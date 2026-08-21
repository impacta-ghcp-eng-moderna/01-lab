# Ajuda completa — Especificar inscrições

## Prompt sugerido

Use o modo **Plan**:

```text
Leia `docs/specs/training-catalog-vertical-slice.md` e inspecione somente o necessário para
entender os contratos atuais da API, persistência, interface e testes.

Precisamos especificar uma nova fatia:
"Permitir o cadastro de inscritos num curso, com nome, sobrenome e e-mail, sem cadastro
separado de alunos, e cada aluno podendo ser inscrito apenas uma vez por curso."

Antes de escrever:
1. liste ambiguidades que bloqueiam um contrato verificável;
2. proponha decisões simples e coerentes com os padrões existentes;
3. mantenha fora do escopo turmas, cadastro global de alunos, autenticação, paginação e CRUD
   completo;
4. não altere arquivos nem implemente código.

Depois que eu aprovar as decisões, crie
`docs/specs/training-attendees-vertical-slice.md` com objetivo, escopo, fora do escopo, dados,
contratos HTTP, comportamento da interface, critérios de aceitação e evidências.
```

## Decisões adequadas ao tempo do lab

- Usar `trainingId` na rota, sem enviá-lo também no corpo.
- Oferecer `POST /api/trainings/{trainingId}/attendees` e
  `GET /api/trainings/{trainingId}/attendees`.
- Gerar `id` no sistema.
- Exigir `firstName`, `lastName` e `email` não vazios; validar formato básico de e-mail.
- Comparar e-mails sem diferença entre maiúsculas/minúsculas e sem espaços externos.
- Retornar `404` quando o treinamento não existir.
- Retornar `409` quando o e-mail já estiver inscrito no mesmo treinamento.
- Permitir o mesmo e-mail em treinamentos diferentes.
- Limitar a interface a cadastro e listagem.

## Estrutura sugerida

```markdown
# Especificação — Inscritos em treinamentos

## Estado
## Objetivo
## Escopo
## Fora do escopo
## Dados do inscrito
## Contrato da API
### Cadastrar inscrito
### Listar inscritos
## Comportamento da interface
## Critérios de aceitação
## Evidências esperadas
## Decisões ainda abertas
```

Revise especialmente se cada critério pode ser observado por resposta HTTP, teste ou fluxo no
navegador. A especificação não deve prescrever classes ou organização interna.
