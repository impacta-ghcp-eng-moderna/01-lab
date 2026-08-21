# Passo 5 — Criar a interface e a navegação

**Tempo sugerido: 15 minutos**

Abra uma nova sessão no modo **Agent**, agora com contexto restrito à interface, aos contratos
compartilhados e à especificação de inscrições.

Crie uma página para gerenciar os inscritos de um treinamento. Ela deve:

- identificar claramente o treinamento selecionado;
- listar os inscritos já cadastrados;
- coletar nome, sobrenome e e-mail;
- representar carregamento, sucesso, lista vazia e erro;
- preservar os dados preenchidos quando a API rejeitar a inscrição;
- atualizar a lista depois de um cadastro bem-sucedido.

Na lista existente de treinamentos, adicione uma ação que leve à página de inscritos do item
selecionado. Não transforme a tela em um CRUD de treinamentos nem adicione navegação que não
seja necessária à fatia.

Execute API e Client em terminais separados e valide no navegador um cadastro válido e uma
tentativa de e-mail duplicado.

> [!TIP]
> Para prompt completo, rotas sugeridas, comandos e roteiro de teste manual, consulte as
> [instruções completas](https://github.com/{{ repository }}/blob/main/.github/help/05-criar-interface-navegacao.md).

Quando o fluxo estiver acessível pela lista de treinamentos, comente `integrado`.
