# Ajuda completa — Ajustar as instruções

## Prompt sugerido

```text
Leia `.github/copilot-instructions.md` e os nomes dos documentos em `docs/specs/`.

A instrução atual referencia sempre uma única especificação, mas o repositório agora possui
fatias independentes. Proponha a menor alteração que torne a seleção de especificações
dependente da tarefa.

Preserve propósito, plataforma e validação. A nova regra deve:
- mandar ler as especificações relevantes antes de planejar ou alterar comportamento;
- exigir que conflitos sejam sinalizados antes da edição;
- exigir contrato explícito para comportamento novo;
- evitar que detalhes de produto sejam duplicados nas instructions;
- não transformar a nova especificação na referência obrigatória para toda solicitação.

Mostre primeiro o trecho atual, o trecho proposto e a justificativa. Aguarde minha aprovação
antes de editar.
```

## Resultado esperado

O arquivo deve continuar curto. Uma formulação adequada é orientar o Copilot a consultar
`docs/specs/` e selecionar os documentos relacionados à tarefa, em vez de apontar
incondicionalmente para `training-catalog-vertical-slice.md`.

## Revisão

- O texto descreve processo de trabalho, não regras detalhadas de inscritos?
- Uma mudança apenas em treinamentos ainda recebe a especificação correta?
- Uma mudança apenas em inscrições recebe a nova especificação?
- Conflitos entre documentos precisam ser apresentados ao usuário?
- Os comandos de validação continuam sendo descobertos no repositório?
