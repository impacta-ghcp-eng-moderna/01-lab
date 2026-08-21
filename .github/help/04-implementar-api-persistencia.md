# Ajuda completa — Implementar API e persistência

## Contrato de referência

Use a especificação aprovada pela equipe como autoridade. Se ela adotou as decisões sugeridas:

| Operação | Rota | Resultado principal |
| --- | --- | --- |
| Cadastrar | `POST /api/trainings/{trainingId}/attendees` | `201 Created` |
| Listar | `GET /api/trainings/{trainingId}/attendees` | `200 OK` |
| Treinamento inexistente | ambas | `404 Not Found` |
| Entrada inválida | cadastro | `400 Bad Request` com `errors` |
| E-mail repetido no treinamento | cadastro | `409 Conflict` com `errors.email` |

## Prompt sugerido

```text
Leia as especificações relevantes em `docs/specs/`, `.github/copilot-instructions.md`, os
contratos em `src/Application`, os endpoints em `src/Api`, o modelo em `src/Infrastructure`
e os padrões em `src/Tests/Api.Tests`.

Implemente somente a fatia de cadastro e listagem de inscritos aprovada na especificação.

Restrições:
- preserve todos os contratos existentes de treinamentos;
- use Entity Framework Core e o SQLite já configurado;
- modele o inscrito como dependente de um treinamento, sem cadastro global de aluno;
- imponha unicidade do e-mail normalizado por treinamento também no banco;
- não imponha unicidade global;
- mantenha detalhes de persistência fora do DTO público;
- retorne 404 para treinamento inexistente;
- gere uma migration, mas pare para revisá-la antes de aplicar;
- use a skill existente de revisão de migration;
- teste pela API pública com banco SQLite isolado;
- não implemente edição, exclusão, autenticação, paginação ou interface.

Antes de editar, apresente:
1. arquivos envolvidos;
2. contratos públicos;
3. entidade, relacionamento e índice composto;
4. estratégia de normalização do e-mail;
5. cenários de teste;
6. comandos de validação.

Aguarde aprovação. Depois implemente em incrementos, gere e revise a migration, aplique-a no
banco de desenvolvimento e execute os testes direcionados.
```

## Cenários mínimos de teste

1. Cadastro válido retorna `201`, localização e representação.
2. Listagem do treinamento contém o inscrito criado.
3. Campo obrigatório inválido retorna `400`.
4. Formato de e-mail inválido retorna `400`.
5. Treinamento inexistente retorna `404`.
6. Mesmo e-mail, variando caixa ou espaços, no mesmo treinamento retorna `409`.
7. O mesmo e-mail pode ser cadastrado em dois treinamentos diferentes.

## Comandos

Confirme o nome da migration proposto pelo agente antes de executar:

```bash
dotnet ef migrations add AddTrainingAttendees \
  --project src/Infrastructure \
  --startup-project src/Api

dotnet ef database update \
  --project src/Infrastructure \
  --startup-project src/Api

dotnet test src/Tests/Api.Tests/TrainingCatalog.Api.Tests.csproj
```

Inspecione a migration gerada. O índice deve representar a combinação de treinamento e e-mail
normalizado, e a chave estrangeira deve apontar para o treinamento.
