# Schemas — Arquitetura de Dados

Documentação das tabelas principais. Serve como referência para escrever queries sem precisar acessar o banco diretamente.

## Convenção de arquivo
`[nome_da_tabela].md` — uma tabela por arquivo

## Convenção de documentação de tabela

```markdown
# Tabela: [nome]

**Database / Schema:** [db.schema]
**Descrição:** o que essa tabela representa

| Coluna | Tipo | Descrição | Nullable |
|---|---|---|---|
| id | UUID | Identificador único | não |
| ... | | | |

**Notas:**
- Qualquer peculiaridade relevante
- Relacionamentos com outras tabelas
```

## Index
(Nenhum schema ainda — adicione as tabelas principais)
