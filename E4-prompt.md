# Prompt usado (E4, página v2)

Agente: Claude (claude.ai) · Claude Opus 5.5. 

> Generá la versión 2 de la página web de un solo archivo (`pagina/index.html`, HTML +
> JavaScript, sin servidor, guardando datos en `localStorage`) que implemente la
> especificación del Grupo 7, frente Cotización de Aseguradora Pampa. Te adjunto la página
> v1 (la de la E3) para que mantengas lo que no cambió.
>
> Usá como única fuente `specs/requirements.md` (con su Historial de cambios),
> `specs/use-cases.md`, `specs/acceptance-criteria.md` y `specs/tarifas-v4.2.md`.
>
> Qué cambió desde la v1 (cambio G7-9, Acta 3.ª §3.1): RF-02 pasó a la versión 2 (el
> sistema registra la fecha de emisión) y se agregaron RF-06 a RF-09: validez de quince
> días corridos, una cotización vencida no se puede aceptar, la cotización nueva no hereda
> el precio de la anterior y la cotización vigente conserva su precio aunque cambie la
> tarifa. Implementalos.
>
> Reglas:
> 1. Implementá solo lo que dice la especificación. No agregues reglas de negocio que no
>    estén escritas, aunque las conozcas por el caso o por la planilla.
> 2. Donde haya un [NEEDS CLARIFICATION] o la especificación no diga algo, no lo
>    resuelvas: mostrá en la página un aviso con la pregunta abierta y quién decide. Los
>    pendientes siguen siendo los de la v1 (descuentos, antigüedad máxima del vehículo),
>    más los nuevos: el día quince de la validez y renovar una cotización vencida con un
>    solo paso.
> 3. Cada parte de la página tiene que indicar con un comentario de qué RF o paso del
>    UC-01 sale.
> 4. Si necesitás algo que la especificación no pide para poder probar un criterio (por
>    ejemplo, simular la fecha de hoy), no lo escondas: listalo como decisión en el plan y
>    marcalo en la página como control de prueba.
> 5. Antes de escribir código, proponé un plan y listá qué decisiones tuviste que tomar
>    porque la especificación no las define. Esperá nuestra aprobación.
