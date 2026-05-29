# 000046 - banco de skills para databricks

- Numero: 000046
- Titulo: banco de skills para databricks
- Dono: tools/DataBricks_IA
- Prioridade: 999
- Status: em-andamento
- Criado em: 2026-05-29
- Atualizado em: 2026-05-29
- Chamado: 
- Skills relacionadas: 

## Objetivo

Implantar um Banco de Skills no Databricks (catalogo `main.skills_management`) com estrutura de dados, governanca de ciclo de vida e pipelines SQL para geracao automatica e revisao periodica de skills.

## Escopo

1. Criar schema e tabelas base de gestao de skills.
2. Implementar pipeline SQL de geracao automatica de skills candidatas a partir de interacoes de chat.
3. Implementar pipeline SQL de revisao periodica das skills ativas.
4. Definir validacoes operacionais para publicacao e acompanhamento (uso, qualidade e historico).
5. Registrar material de referencia do plano na pasta `materiais/`.

## Atividades

| # | Atividade | Status | Skill executora | Saida |
|---|---|---|---|---|
| A1 | Estruturar DDL do schema `main.skills_management` com tabelas de registry, versions, reviews, usage logs, chat interactions e candidates | pendente | redshift-sql-specialist | `sql/01_schema_e_tabelas.sql` |
| A2 | Consolidar pipeline semanal de geracao automatica de skills candidatas (clusterizacao/classificacao/geracao/insert/update) | pendente | redshift-sql-specialist | `sql/02_pipeline_geracao_skills.sql` |
| A3 | Consolidar pipeline mensal de revisao periodica de skills com criterios de qualidade e acoes | pendente | redshift-sql-specialist | `sql/03_pipeline_revisao_skills.sql` |
| A4 | Definir checklist de execucao operacional no Databricks Workflows (agendamento, ordem e rollback) | pendente | technical-writer | `operacao/checklist_execucao.md` |
| A5 | Validar consistencia de tipos, constraints e comentarios para governanca de dados | pendente | syg-sonarcloud-specialist | `validacao/relatorio_consistencia.md` |

## Criterios de aceite

1. Todos os objetos SQL do modelo do PDF estao representados em arquivos versionados no projeto.
2. O pipeline semanal grava candidatas e marca interacoes processadas sem ambiguidade de status.
3. O pipeline mensal identifica skills para revisao e define saida acionavel para melhoria/deprecacao.
4. Existe checklist claro para execucao no Databricks Workflow.
5. O material original do plano esta armazenado em `materiais/`.

## Skills recomendadas atuais

- maintain-planner
- redshift-sql-specialist
- technical-writer
- syg-sonarcloud-specialist

## Riscos

- Divergencias entre funcoes SQL disponiveis no workspace Databricks e o script de referencia.
- Campos de texto longo sem padronizacao podem dificultar auditoria de versoes.
- Falta de agendamento/monitoramento dos workflows pode interromper a governanca continua.
