# Passo 3 — Ajustar o contexto durável

**Tempo sugerido: 5 minutos**

Leia `.github/copilot-instructions.md`. A instrução atual foi escrita quando só existia a
primeira fatia vertical e manda o Copilot consultar sempre a especificação do catálogo.
Agora há mais de uma especificação, então essa regra pode fornecer contexto incompleto ou
indevido.

Use o Copilot para propor uma alteração mínima que:

- preserve propósito, plataforma e validações existentes;
- exija a leitura das especificações relevantes para a solicitação atual;
- não trate uma especificação antiga como autoridade para todo comportamento futuro;
- exija contrato explícito para novos comportamentos e sinalização de conflitos;
- não copie os detalhes da nova especificação para o arquivo de instruções.

Revise o diff antes de aceitar. `copilot-instructions.md` deve orientar **como trabalhar** no
repositório; `docs/specs/` deve registrar **o que o produto deve fazer**.

> [!TIP]
> Para um prompt pronto e critérios de revisão, consulte as
> [instruções completas](https://github.com/{{ repository }}/blob/main/.github/help/03-ajustar-instrucoes.md).

Quando a instrução estiver atualizada e revisada, comente `contextualizado`.
