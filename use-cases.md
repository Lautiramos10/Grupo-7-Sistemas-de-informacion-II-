# Casos de uso

## UC-01: Cotizar seguro automotor

**Actor:PAS**

**Precondición:El PAS esta identificado en el sistema**

**Flujo principal:**
1. El PAS inicia una cotizacion.
2. El PAS ingresa los datos del vehiculo y del conductor
3. El PAS elige la cobertura (Responsabilidad Civil, Terceros Completos o Todo Riesgo)
4. Se ejecuta UC-02 Obtener version de tarifas vigente (include)
5. El sistema calcula el precio con esa version y se lo muestra al PAS
6. El sistema registra la cotizacion con sus datos, la cobertura, la version de tarifas, el precio y la fecha

**Flujo(s) alternativo(s):**
- 5a: El cliente tiene condiciones de descuento: se ejecuta UC-03 Aplicar descuentos (extend) y el sistema calcula el precio con descuento.
- 2a: El vehiculo supera la antigüedad maxima: [NEEDS CLARIFICATION: M. Duarte dice 20 años; S. Roldan dice hasta 25 con otra poliza. Decide M. Duarte]
- 6a. Validez de la cotizacion: [NEEDS CLARIFICATION: el caso no dice cuanto mantiene el precio. Decide M. Duarte]

**Postcondición: La cotizacion queda registrada con su precio, la version de tarifas y la fecha.**

**Relaciones con otros casos de uso:**

| Relación | Caso de uso relacionado | Tipo (include/extend) | Justificación |
|----------|--------------------------|------------------------|----------------|
|UC-01 → UC-02 | Obtener version de tarifas vigente | include | Siempre se ejecuta: sin una versión de tarifas no hay precio, y hoy nadie sabe que version usó cada PAS (Caso §3.1) |
| UC-03 → UC-01 | Aplicar descuentos | extend | Solo ocurre si el cliente cumple condiciones de descuento; el flujo base esta completo sin el [NEEDS CLARIFICATION: tope o suma de descuentos y definicion de VIP; decide M. Duarte] |


Recordar (ver skill/SKILL.md): include = siempre se ejecuta como parte
del flujo, sin excepción. extend = extiende opcionalmente bajo una
condición específica, el flujo base es completo sin ella. Toda relación
sin justificación no cuenta como completa.

## Fragmentos considerados para este caso de uso

Listar qué fragmentos del relevamiento se usaron para armar este caso
de uso, y qué parte del flujo justifica cada uno.

| Fragmento | Qué aporta al caso de uso |
|-----------|------------------------------|
| Caso §3.1 | El orden del flujo: datos del vehículo y del conductor, precio, comunicación al cliente |
| Caso §3.1 (situación observada) y §6 | El include de la versión de tarifas y las tres coberturas típicas |
| Voces de J. Ponce y H. Vidal (§4) | El extend de descuentos y su conflicto abierto |