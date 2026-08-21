# Passo 4 — Implementar API e persistência

**Tempo sugerido: 20 minutos**

Abra uma nova sessão no modo **Agent** e forneça como contexto a nova especificação, os
contratos existentes, o `DbContext` e os testes da API.

Peça um plano curto antes das edições. A implementação deve atravessar somente as camadas
necessárias para:

- cadastrar um inscrito em um treinamento;
- listar os inscritos desse treinamento;
- persistir os dados com Entity Framework Core e SQLite;
- impedir no banco e na API que o mesmo e-mail seja inscrito duas vezes no mesmo treinamento;
- preservar os contratos existentes de treinamentos;
- gerar e revisar uma migration antes de aplicá-la;
- comprovar os principais contratos com testes pela API pública.

Use a skill de revisão de migration já disponível no repositório. Confirme que a unicidade é
por treinamento, e não global, e que um treinamento inexistente não recebe inscrições.

> [!TIP]
> Para contratos sugeridos, prompt completo, cenários de teste e comandos, consulte as
> [instruções completas](https://github.com/{{ repository }}/blob/main/.github/help/04-implementar-api-persistencia.md).

Quando API, migration e testes direcionados estiverem concluídos, comente `persistido`.
