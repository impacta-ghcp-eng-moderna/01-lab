# Ajuda completa — Validar a entrega

## Comandos

```bash
dotnet restore src/TrainingCatalog.slnx
dotnet build src/TrainingCatalog.slnx --no-restore
dotnet test src/TrainingCatalog.slnx --no-build
git diff --check
git status --short
```

## Matriz de evidências

| Critério | Evidência mínima |
| --- | --- |
| entrada válida | resposta `201` e teste automatizado |
| validação de campos | resposta `400` e teste |
| treinamento inexistente | resposta `404` e teste |
| e-mail duplicado por treinamento | resposta `409`, teste e índice composto |
| mesmo e-mail em treinamentos diferentes | teste automatizado |
| persistência | consulta após cadastro e migration revisada |
| listagem | resposta `200`, teste e tela preenchida |
| acesso pela lista | navegação executada no navegador |
| erro na interface | duplicidade exibida sem apagar o formulário |

## Prompt de revisão final

Selecione o custom agent de revisão criado no walkthrough ou use o modo **Ask**:

```text
Leia as especificações relevantes e revise o diff atual sem editar.

Relacione cada critério de aceitação da fatia de inscritos a uma evidência concreta em teste,
contrato, migration ou interface. Execute somente os comandos documentados de build e testes.

Procure especialmente:
- contrato implementado diferente da especificação;
- unicidade global em vez de unicidade por treinamento;
- comparação de e-mail sensível a caixa ou espaços;
- ausência de 404 para treinamento inexistente;
- UI que perde dados em erro;
- regressão nos endpoints de treinamentos.

Informe primeiro falhas verificáveis, depois lacunas de evidência. Não sugira funcionalidades
fora do escopo.
```

Se alguma evidência faltar, corrija apenas essa lacuna e repita a validação direcionada.
