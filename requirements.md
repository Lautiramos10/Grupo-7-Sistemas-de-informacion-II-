# Requerimientos

Completar a partir de los fragmentos de relevamiento del caso. Seguir
la convención de `skill/SKILL.md` (atómico, verificable, sin tecnología
mezclada).

## Requerimientos funcionales

| ID | Issue |Requerimiento | Nivel/tipo | Fragmento(s) de origen | verificacion |
|----|---------------|--------------------------|
| RF-01 | G7-2 | El sistema debe permitir al PAS obtener un precio de seguro automotor ingresando los datos del vehiculo, del conductor y la cobertura elegida| Usuario/Funcional | Caso 3.1 y 7; voz de A. Pampin (4) | Sin alguno de los tres datos no devuelve precio |
| RF-02 | G7-3 | El sistema debe registrar cada cotizacion con sus datos de entrada, su precio y su fecha de emision | Sistema/funcional | Caso §2.1 y §3.1; Acta 3.ª §3.1 | De cualquier cotizacion se pueden consultar vehiculo, conductor, cobertura, precio y fecha de emisión.|
| RF-03 | G7-4 | El sistema debe registrar la versión de tarifas con la que se calculó cada cotización | Sistema / F | Caso §3.1 | En cualquier cotización se ve la versión de tarifas usada. |
| RF-04 | G7-5 | Dos cotizaciones con el mismo vehículo, conductor, cobertura y versión de tarifas deben dar el mismo precio, sin importar qué PAS las pida | Negocio / F | Caso §3.1 | Se cotiza el mismo caso con dos PAS distintos: los precios son iguales |
| RF-05 | G7-6 | El sistema debe aplicar descuentos al precio cotizado según las condiciones del cliente. [NEEDS CLARIFICATION: H. Vidal dice que los descuentos están topeados y no se acumulan; J. Ponce dice que se suman (débito automático, otra póliza y antigüedad). Además M. Duarte y R. Ferreyra definen distinto al cliente VIP. Decide M. Duarte.] | Negocio / F | Voces de M. Duarte, H. Vidal, J. Ponce y R. Ferreyra (§4) | Pendiente: no se puede definir hasta decidir si se acumulan y qué es un VIP. |
| RF-06 | G7-10 | El sistema debe considerar vencida a toda cotización cuando pasaron quince días corridos desde su fecha de emisión | Negocio / F | Acta 3.ª §3.1 | Una cotización emitida el 02/11/2026 figura vigente el 16/11/2026 y vencida el 18/11/2026 |
| RF-07 | G7-11 | El sistema no debe permitir aceptar una cotización vencida | Negocio / F | Acta 3.ª §3.1 | Al intentar aceptar una cotización vencida, el sistema no la acepta y avisa que hay que cotizar de nuevo |
| RF-08 | G7-12 | El sistema debe calcular toda cotización nueva con la tarifa vigente, sin heredar el precio de una cotización anterior | Negocio / F | Acta 3.ª §3.1 | 	Al cotizar de nuevo los mismos datos de una cotización vencida, el precio se calcula con la tarifa vigente y no se copia el de la vencida |
| RF-09 | G7-13 | 	El sistema debe mantener el precio de una cotización vigente aunque cambie la tarifa, hasta que la cotización venza | Negocio / F | Acta 3.ª §3.1 | Una cotización vigente sigue mostrando su precio y su versión después de publicarse una versión nueva de tarifas |

## Fragmentos que NO son requerimientos funcionales

| Fragmento | Texto | Categoría | Justificación |
|-----------|-------|-----------|----------------|
| A. Pampín (§4) | «Quiero un sistema rápido, moderno y fácil de usar. Que el productor lo pueda usar sin capacitación.» | RNF | Cualidades sin métrica: no se puede verificar con un sí o un no |
| A. Pampín (§7) | «Tenemos que estar funcionando antes de que se jubile Héctor» | Objetivo de negocio | Es un plazo del proyecto, no una función del sistema |
| Caso §3.1 | El PAS usa una planilla Excel descargada del sitio | Dato de contexto | Describe cómo se trabaja hoy; no pide nada del sistema nuevo |
| Caso §3.1 | El PAS pasa el precio al cliente por WhatsApp o por teléfono | Dato de contexto | Describe el proceso actual; el caso no pide cambiarlo |
| J. Ponce (Acta 3.ª §3.1) | «Dos semanas, por lo menos. El cliente compara con otras compañías» | Dato de contexto | Es el argumento de un plazo que la decisión fijó en quince días: el requerimiento es RF-06 |

## Conflictos u observaciones detectadas

- Descuentos: H. Vidal dice que están topeados; J. Ponce dice que se suman. [NEEDS CLARIFICATION: decide M. Duarte.] El acta de la tercera reunión confirma que este punto sigue abierto.
- Antigüedad máxima del vehículo: M. Duarte dice 20 años; S. Roldán dice hasta 25 con otra póliza. [NEEDS CLARIFICATION: decide M. Duarte.]
- Día 15 de la validez: el acta no dice si el día quince todavía cuenta como vigente. [NEEDS CLARIFICATION: decide M. Duarte.]
- Renovación de una cotización vencida «con un solo paso»: el acta lo deja abierto (4.1, M. Duarte, 20/11/2026). No se especifica.

## Historial de cambios

| Req. | Versión | Fecha | Qué cambió | Issue |
|------|---------|-------|------------|-------|
| RF-02 | v1 | 19/10 | «…su precio y su fecha.» | G7-3 |
| RF-02 | v2 | 12/11 | Pasa a «fecha de emisión»: lo decide M. Duarte en el Acta 3.ª §3.1 | G7-9  |
| RF-06 | v1 | 12/11 | Nuevo: validez de quince días corridos (Acta 3.ª §3.1) | G7-10 |
| RF-07 | v1 | 12/11 | Nuevo: una cotización vencida no se puede aceptar (Acta 3.ª §3.1) | G7-11 |
| RF-08 | v1 | 12/11 | Nuevo: la cotización nueva no hereda el precio (Acta 3.ª §3.1) | G7-12 |
| RF-09 | v1 | 12/11 | Nuevo: la cotización vigente conserva su precio si cambia la tarifa (Acta 3.ª §3.1) | G7-13 |
