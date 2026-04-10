## 1) Confirmar que o processo está rodando e pegar PID
ps aux | grep '\[r\]clone copy'

## 2) Ver as últimas linhas do log (rápido)
tail -n 80 /var/log/rclone-imagens-full.log

## 3) Acompanhar em tempo real (follow)
tail -f /var/log/rclone-imagens-full.log

## 4) Ver só erros (se existirem)
grep -nE 'ERROR|Failed|429|503|timeout|Unauth|unauth' /var/log/rclone-imagens-full.log | tail -n 200

## 5) Ver tamanho já baixado (progresso físico no disco)
du -sh /mnt/onedrive_tmp/Imagens
df -hT /mnt/onedrive_tmp

## 6) Contagem de arquivos já baixados
find /mnt/onedrive_tmp/Imagens -type f | wc -l

## 7) Conferir “velocidade média” a partir do log (quando houver stats)
grep -E 'Transferred:' /var/log/rclone-imagens-full.log | tail -n 20

---

# ETA (estimativa de tempo)

## Regra prática
O ETA só aparece quando o rclone está emitindo linhas de *stats/progress* (com taxa/bytes). 
No seu modo atual, o log está majoritariamente em “Copied (new)” e “Set directory modification time”, que não carregam ETA.

## Melhor forma: iniciar o job já logando stats com ETA
(para próximos runs; isso grava linhas periódicas com taxa e ETA no log)

nohup rclone copy "onedrive:Imagens" "/mnt/onedrive_tmp/Imagens" \
  --transfers 1 --checkers 2 \
  --tpslimit 3 --tpslimit-burst 3 \
  --retries 30 --low-level-retries 200 --retries-sleep 10s \
  --timeout 2m --contimeout 30s \
  --drive-chunk-size 32M \
  --create-empty-src-dirs \
  --fast-list \
  --stats 30s \
  --stats-one-line \
  --stats-log-level NOTICE \
  --log-file /var/log/rclone-imagens-full.log --log-level INFO \
  >/var/log/rclone-imagens-full.out 2>&1 &
disown

Depois, para ver ETA:
tail -f /var/log/rclone-imagens-full.log | grep -E 'Transferred:|NOTICE'

\[Não verificado\] Alguns usuários tentam “forçar” uma linha de progresso via sinal (SIGUSR1), mas isso não é comportamento garantido; há discussão como *feature request* no fórum do rclone.  \[oai_citation:0‡rclone forum\](https://forum.rclone.org/t/signal-to-make-rclone-output-an-extra-line-of-current-progress/44588?utm_source=chatgpt.com)

---

# \[Inferência\] ETA aproximado sem stats do rclone
(útil se você não quiser reiniciar o job)

1) Total remoto:
rclone size "onedrive:Imagens"

2) Total local:
du -sb /mnt/onedrive_tmp/Imagens | awk '{print $1}'

3) Taxa recente:
- Se o log não tem linhas “Transferred: …, …/s”, não dá para estimar ETA de forma confiável sem medir throughput por fora.

---

# Encerrar o job (se precisar)
pkill -f 'rclone copy.*onedrive:Imagens'
# ou pelo PID:
kill <PID>