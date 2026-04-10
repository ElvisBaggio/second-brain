Segue a consolidação objetiva dos pontos relevantes, decisões e itens acionáveis (ToDos) extraídos da reunião.

### Decisões e alinhamentos
- Remover “junk”/scopes na URL e enviar o usuário direto para /signup com parâmetro de contexto (ex.: full=Console Magalu Cloud) e mini-branding no header do ID Magalu para indicar Magalu Cloud.
- Não inserir perguntas nem forks antes da criação do ID; reduzir cliques do fluxo de ID (alvo: de 4 para 2).
- Pivô PF/PJ acontecer no console antes dos dados de faturamento; evitar cobrança com cartão PF quando a intenção é PJ.
- Unificar Termos de Uso e Política de Privacidade em uma única tela com dois checkboxes, com opção de download PDF datado em formato ISO.
- Onboarding opcional e não modal na home do console (CTA “Getting started” com vídeo/gif curto), sujeito a teste A/B.
- Padronizar exibição de IDs de erro/trace com prefixo identificável (ex.: MGC-TRACE-<id>).

### Problemas observados (UX/fluxos)
- Bloqueio de copiar/colar no campo de confirmação (e-mail/PIN) gera fricção e não inibe automação; ausência de métricas sobre efetividade.
- Campo de PIN sem autofocus; comportamento inconsistente de Ctrl+C/Ctrl+V (Firefox no Ubuntu) e colagem concentrando tudo no primeiro input.
- E-mail de verificação sem botão “Copiar código”.
- Após confirmar o e-mail/PIN, usuário é redirecionado ao /login em vez de entrar direto no console.
- “Completar dados”: botão no banner funciona, outros pontos não redirecionam (janela some, sem redirect).
- Portlet de VMs não carrega na primeira tentativa; experiência considerada “péssima”.
- Linguagem “Documento para emissão de nota fiscal” assusta; preferir “Dados de faturamento”.
- Termos/Política em duas páginas gerando etapas desnecessárias; ausência de PDFs versionados.
- Política de senha rejeita passphrases longas (ex.: “one horse many drivers”); desalinhada com recomendações modernas (NIST).

### Itens acionáveis (ToDos)
- Implementar roteamento direto para /signup com parâmetro de contexto e mini-branding no header do ID Magalu; Critério: URL limpa, página de create/ID com indicação “Magalu Cloud”.
- Unificar Termos e Política em uma única tela com dois checkboxes, links e botões de download de PDFs datados (ex.: MGC_Termos_20250925.pdf, MGC_Privacidade_20250925.pdf); Critério: aceite em uma única etapa e arquivos acessíveis.
- Após verificação do e-mail/PIN, realizar login automático e levar ao console; Critério: zero retorno ao /login sem necessidade.
- Ajustar “Completar dados” para redirecionar de todos os pontos (banner e links); Critério: clique sempre leva à página correta.
- Adicionar autofocus no primeiro campo do PIN e permitir colagem; incluir botão “Copiar código” no e-mail; corrigir comportamento no Firefox/Ubuntu; Critério: colagem funcional e estável em navegadores suportados.
- Revisar política de senha segundo NIST (permitir passphrases longas, remover exigências arbitrárias, usar blacklist de senhas comuns); Critério: aceitar frases de 15+ caracteres e relatório de impacto.
- Prefixar IDs/erros/trace (ex.: MGC-TRACE-<id>) em todos os serviços, incluindo Block Storage; Critério: todos os IDs exibidos ao usuário com prefixo consistente.
- Detectar domínio corporativo para sugerir PJ no pivô (heurística de provedores públicos); Critério: sugestão visível quando e-mail não pertencer à lista de provedores públicos.
- Implementar pivô PF/PJ em etapa única antes de faturamento (campo CPF ou CNPJ com validação); Critério: seleção e validação sem sair do fluxo.
- Corrigir portlet de VMs que não carrega na primeira tentativa; Critério: carregamento consistente ou erro claro com trace id prefixado.
- Substituir textos por “Dados de faturamento” e ajustar microcopy para reduzir ansiedade; Critério: nova cópia publicada e validada.
- Criar CTA “Getting started” não modal com vídeo/gif de 30s e link de walkthrough; Critério: presença do CTA sem bloquear ações.

### Experimentos e métricas
- Medir conversão: signup → console → ativação da conta → primeiro recurso criado; Critério: dashboard com funil e abandono por etapa.
- Teste A/B: permitir vs. bloquear colagem no PIN/confirm e impacto em conversão e tempo de conclusão; Critério: resultado estatisticamente significativo.
- Teste A/B: home com CTA de onboarding vs. sem CTA; Critério: impacto em ativação e criação do primeiro recurso.
- Telemetria de erros de colagem/teclas (PIN) e de falhas de carregamento (portlets); Critério: eventos padronizados com trace prefixado.

### Conteúdo e onboarding
- Publicar PDFs versionados e datados em repositório/armazenamento com naming consistente (prefixo MGC e data ISO); Critério: links de download servindo arquivos corretos.
- Considerar agenda de sessões semanais para iniciantes (inscrição via formulário); Critério: página/CTA de inscrição e calendário publicados.

### Nomenclatura e observabilidade
- Adotar prefixos claros para IDs de erro/trace e expor em todas as mensagens de erro exibidas ao usuário; Critério: suporte consegue identificar rapidamente o contexto pelo prefixo.

### Dependências e dúvidas em aberto
- Confirmar referência normativa de senha (“NIST 2024” citado) e versão aplicável (provável NIST SP 800-63B); Critério: decisão documentada.
- Verificar limites do template do serviço de e-mail para incluir botão “Copiar código”; Critério: PoC no provedor atual.
- Checar viabilidade de mini-branding no header do ID Magalu (constraints do sistema de identidade); Critério: OK técnico ou alternativa definida.
- Definir processo de geração, versionamento e hospedagem dos PDFs datados; Critério: pipeline e local padrão acordados.

Fontes