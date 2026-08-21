# Passo 6 — Validar a fatia completa

**Tempo sugerido: 5 minutos**

Antes de encerrar, relacione cada critério da especificação a uma evidência. Não use apenas a
aparência da interface como prova de que persistência e regras de negócio estão corretas.

Confirme:

1. build e testes existentes continuam passando;
2. os novos testes exercitam a API pública;
3. a migration representa relacionamento e unicidade esperados;
4. o mesmo e-mail pode existir em treinamentos diferentes, mas não duas vezes no mesmo;
5. a interface é alcançada pela lista de treinamentos;
6. sucesso, lista vazia, treinamento inexistente e duplicidade têm comportamento útil;
7. API e Client continuam usando os contratos documentados.

Revise o diff final e registre qualquer divergência conhecida em vez de escondê-la.

> [!TIP]
> Para comandos, matriz de evidências e roteiro final, consulte as
> [instruções completas](https://github.com/{{ repository }}/blob/main/.github/help/06-validar-entrega.md).

Quando as evidências estiverem reunidas, comente `validado`.
