# Requerimientos

Completar a partir de los fragmentos de relevamiento del caso. Seguir
la convención de `skill/SKILL.md` (atómico, verificable, sin tecnología
mezclada).

## Requerimientos funcionales

| ID | Issue |Requerimiento | Nivel/tipo | Fragmento(s) de origen | verificacion |
|----|---------------|--------------------------|
| RF-01 | G7-2 | El sistema debe permitir al PAS obtener un precio de seguro automotor ingresando los datos del vehiculo, del conductor y la cobertura elegida| Usuario/Funcional | Caso 3.1 y 7; voz de A. Pampin (4) | Sin alguno de los tres datos no devuelve precio |
| RF-02 | G7-3| 3	El sistema debe registrar cada cotizacion con sus datos de entrada, su precio y su fecha | Sistema/funcional | Caso 2.1 y 3.1; | De cualquier cotizacion se pueden consultar vehiculo, conductor, cobertura, precio y fecha|
| RF-03 | G7-4 | El sistema debe registrar la versión de tarifas con la que se calculó cada cotización | Sistema / F | Caso §3.1 | En cualquier cotización se ve la versión de tarifas usada. |
| RF-04 | G7-5 | Dos cotizaciones con el mismo vehículo, conductor, cobertura y versión de tarifas deben dar el mismo precio, sin importar qué PAS las pida | Negocio / F | Caso §3.1 | Se cotiza el mismo caso con dos PAS distintos: los precios son iguales |
| RF-05 | G7-6 | El sistema debe aplicar descuentos al precio cotizado según las condiciones del cliente. [NEEDS CLARIFICATION: H. Vidal dice que los descuentos están topeados y no se acumulan; J. Ponce dice que se suman (débito automático, otra póliza y antigüedad). Además M. Duarte y R. Ferreyra definen distinto al cliente VIP. Decide M. Duarte.] | Negocio / F | Voces de M. Duarte, H. Vidal, J. Ponce y R. Ferreyra (§4) | Pendiente: no se puede definir hasta decidir si se acumulan y qué es un VIP. |

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

-
