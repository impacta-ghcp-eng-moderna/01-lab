# Ajuda completa — Preparar o ambiente

## Comandos

```bash
git switch inicio
dotnet --version
dotnet restore src/TrainingCatalog.slnx
dotnet build src/TrainingCatalog.slnx --no-restore
dotnet test src/TrainingCatalog.slnx --no-build
```

O SDK deve ser .NET 10 e build/testes devem concluir antes da nova implementação.

## Mapa mínimo

Localize:

- `docs/specs/training-catalog-vertical-slice.md`: contrato da fatia existente;
- `.github/copilot-instructions.md`: contexto automático do repositório;
- `src/Application`: contratos compartilhados;
- `src/Api/Program.cs`: endpoints mínimos;
- `src/Infrastructure`: entidade, `DbContext` e migrations;
- `src/Client/Pages`: interface Blazor;
- `src/Tests/Api.Tests`: testes pela API pública.

Não corrija problemas nem peça a implementação de inscritos neste passo. Se a linha de base
falhar, registre o comando e o erro para separar falha preexistente de regressão.
