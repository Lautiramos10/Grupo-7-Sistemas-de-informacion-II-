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

Para cada fragmento del relevamiento que no calificó como RF, clasificar
según las categorías de `skill/SKILL.md` (objetivo/meta de negocio,
restricción técnica, RNF, dato de contexto) y justificar en una línea
por qué no es un RF.

| Fragmento | Texto | Categoría | Justificación |
|-----------|-------|-----------|----------------|
| | | | |
| | | | |

## Conflictos u observaciones detectadas

Si al procesar los fragmentos aparece un conflicto de valores (ver
"Detección de conflictos" en la skill), documentarlo acá aunque no
afecte directamente un RF puntual.

## Historial de cambios

| Req. | Versión | Fecha | Qué cambió | Issue |
|------|---------|-------|------------|-------|
| RF-02 | v1 | 19/10 | «…su precio y su fecha.» | G7-3 |
| RF-02 | v2 | 12/11 | Pasa a «fecha de emisión»: lo decide M. Duarte en el Acta 3.ª §3.1 | G7-9  |
