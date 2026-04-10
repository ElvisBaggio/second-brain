# GTD + Claude — Como usar

## O ciclo completo

```
CAPTURAR → PROCESSAR → ORGANIZAR → REVISAR → FAZER
```

---

## 1. Capturar — joga tudo no Inbox

Qualquer coisa que surgiu: ideia, reunião, tarefa, link, pensamento.

```bash
brain "adiciona ao inbox: [sua captura aqui]"
```

Ou direto no Obsidian: abre `00 Inbox/` e cria nota rápida.

---

## 2. Processar — Claude processa o Inbox

```bash
brain "processa meu inbox"
```

Para cada item do Inbox, aplica as perguntas GTD:
- É acionável? → tem `- [ ]` próxima ação
- Leva menos de 2 min? → faz na hora (ou lembra)
- É referência? → vai para `03 Resources/`
- É projeto? → vai para `01 Projects/` com template
- É algum dia/talvez? → tag `#someday`
- É lixo? → deleta

---

## 3. Organizar — tudo no lugar certo com links

Ao processar, Claude cria `[[links]]` entre notas relacionadas.
Exemplo: reunião do MGC fica em `02 Areas/Trabalho/` e linkada no `01 Projects/Produto MGC/INDEX`.

---

## 4. Revisar — Weekly Review toda sexta

```bash
brain "weekly review"
```

Claude varre o vault e mostra:
- Projetos sem próxima ação definida
- Inbox com itens não processados
- `#someday` para revisitar
- O que foi concluído na semana

---

## 5. Fazer — você age, Claude registra

Depois de uma reunião:
```bash
brain "adiciona ao 1:1 do Cousin: [resumo]"
```

Depois de concluir projeto:
```bash
brain "fecha o projeto Geo Expert e arquiva"
```

---

## Interações cotidianas

| Situação | Comando |
|---|---|
| Ideia rápida | `brain "inbox: [ideia]"` |
| Saiu de reunião | `brain "1:1 Cousin: [anotações]"` |
| Quer saber o que fazer | `brain "quais são minhas próximas ações abertas?"` |
| Fim de semana | `brain "weekly review"` |
| Começo do dia | `brain "resume meu dia de hoje"` |
| Algo novo surgiu | `brain "isso é projeto ou área?"` |

---

## O segredo do híbrido

O **GTD** cuida da ação — o que fazer agora e o que não esquecer.
O **segundo cérebro** cuida do conhecimento — o que você aprendeu e pode reusar.

O **Claude** conecta os dois: ao processar uma reunião, cria a ação no projeto e extrai o aprendizado para `03 Resources/` se houver algo generalizável.

---

## Links úteis
- [[CLAUDE.md]] — instruções do sistema para o Claude
- [[Templates/Daily Note]] — template do diário
- [[Templates/1:1]] — template de 1:1
- [[Templates/Projeto]] — template de projeto
- [[01 Projects/Produto MGC/INDEX]] — projeto principal
- [[02 Areas/Trabalho/Dashboard]] — hub de trabalho
