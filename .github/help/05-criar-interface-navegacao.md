# Ajuda completa — Criar interface e navegação

## Prompt sugerido

```text
Leia a especificação de inscritos em `docs/specs/`, os contratos compartilhados em
`src/Application`, a página atual em `src/Client/Pages/Index.razor` e os padrões visuais do
Client.

Implemente a interface da fatia de inscritos sem alterar a API.

Crie uma página com rota `/trainings/{trainingId:guid}/attendees` que:
- identifica o treinamento;
- carrega e lista seus inscritos;
- apresenta estado vazio;
- coleta nome, sobrenome e e-mail;
- impede envio repetido enquanto a requisição está em andamento;
- apresenta sucesso e atualiza a lista;
- apresenta erros de campo e de negócio sem apagar os dados preenchidos.

Na lista de treinamentos, adicione para cada item uma ação clara que navegue para essa página.

Restrições:
- reutilize MudBlazor e os padrões existentes;
- reutilize os contratos compartilhados;
- não implemente edição ou exclusão;
- não altere endpoints ou persistência;
- não misture o formulário de inscritos ao formulário de criação de treinamento.

Antes de editar, mostre um plano curto, os arquivos envolvidos e o fluxo dos estados da tela.
Ao final, execute as validações e descreva como testar sucesso e duplicidade no navegador.
```

## Execução

Terminal da API:

```bash
dotnet run --project src/Api --launch-profile http --urls http://127.0.0.1:5080
```

Terminal do Client:

```bash
dotnet run --project src/Client --launch-profile http --urls http://127.0.0.1:5152
```

## Roteiro manual

1. Cadastre ou localize um treinamento na página inicial.
2. Use a nova ação desse item para abrir a página de inscritos.
3. Confirme o estado vazio.
4. Cadastre um inscrito e confira a mensagem e a lista atualizada.
5. Tente novamente com o mesmo e-mail em outra combinação de caixa e espaços.
6. Confirme a mensagem útil e a preservação dos campos.
7. Volte à lista e verifique se a navegação continua funcional.
