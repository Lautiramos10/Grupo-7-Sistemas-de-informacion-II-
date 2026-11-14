# Criterios de aceptación — Frente Cotización (G7)

Formato Dado / Cuando / Entonces. Cada criterio nombra el requerimiento y el issue
de Jira que valida. Los valores esperados se calcularon con la versión de tarifas
4.2 (`tarifas-v4.2.md`). Los criterios que dependen de una decisión abierta quedan
marcados con [NEEDS CLARIFICATION] y no se ejecutan hasta que decida M. Duarte.

**Datos del caso base (CB):** vehículo año 2021, zona CABA, guarda en garaje SÍ;
conductor de 30 años con 0 siniestros en los últimos 24 meses; cobertura Terceros
Completos (TC). Con tarifas 4.2: 32.000 × 1,15 × 1,00 × 1,25 × 0,90 × 1,00 = **$41.400**.

| ID | Requerimiento | Dado / Cuando / Entonces |
|----|---------------|--------------------------|
| CA-01 | RF-01 · G7-2 | **Dado** un PAS identificado y la versión de tarifas 4.2 vigente, **cuando** ingresa los datos del vehículo y del conductor del CB, elige la cobertura TC y pide cotizar, **entonces** el sistema muestra el precio $41.400. |
| CA-02 | RF-01 · G7-2 | **Dado** un PAS identificado, **cuando** pide cotizar con los datos del vehículo y del conductor del CB pero sin elegir cobertura (y, en otra prueba, sin la edad del conductor, y sin el año del vehículo), **entonces** el sistema no muestra ningún precio e indica qué dato falta. |
| CA-03 | RF-02 · G7-3 | **Dado** que el PAS cotizó el CB, **cuando** consulta el registro de cotizaciones, **entonces** la cotización aparece con los datos del vehículo, los del conductor, la cobertura, el precio ($41.400) y la fecha de emisión (en este caso, 02/11/2026) |
| CA-04 | RF-03 · G7-4 | **Dado** que la versión de tarifas vigente es 4.2, **cuando** el PAS cotiza el CB y luego consulta esa cotización en el registro, **entonces** la cotización indica "versión de tarifas 4.2"; **y dado** que después se publica una versión nueva, **cuando** se consulta la misma cotización, **entonces** sigue indicando 4.2. |
| CA-05 | RF-04 · G7-5 | **Dado** dos PAS distintos identificados y la misma versión de tarifas 4.2, **cuando** cada uno cotiza el CB, **entonces** los dos precios son iguales ($41.400). |
| CA-06 | RF-05 · G7-6 | **Dado** un cliente del CB con débito automático, otra póliza vigente y 6 años de antigüedad como cliente, **cuando** el PAS cotiza, **entonces** el precio refleja los descuentos que correspondan. [NEEDS CLARIFICATION: si se suman los tres (20 % → $33.120, J. Ponce) o tienen tope (H. Vidal), y qué es un cliente VIP. Decide M. Duarte.] |
| CA-07 | UC-01 · 2a | **Dado** un vehículo año 2003 (23 años) con el resto de los datos del CB, **cuando** el PAS pide cotizar, **entonces** [NEEDS CLARIFICATION: se rechaza por superar 20 años (M. Duarte) o se acepta hasta 25 si el cliente tiene otra póliza (S. Roldán). Decide M. Duarte.] |
| CA-08 | RF-06 · G7-10 | Dado una cotización del CB emitida el 02/11/2026, cuando se consulta el 16/11/2026 (14 días corridos), entonces figura vigente; y cuando se consulta el 18/11/2026 (16 días corridos), entonces figura vencida. [NEEDS CLARIFICATION: el día 17 (quince días) no se prueba hasta que decida M. Duarte si cuenta como vigente.] |
| CA-09 | RF-07 · G7-11 | Escenario A. Dado una cotización del CB emitida el 02/11/2026 y vencida, cuando el PAS intenta aceptarla el 18/11/2026, entonces el sistema no la acepta y le avisa que debe cotizar de nuevo. Escenario B. Dado la misma cotización, cuando el PAS la acepta el 10/11/2026 (8 días corridos), entonces el sistema la acepta |
| CA-10 | RF-08 · G7-12 | Dado una cotización del CB vencida con precio $41.400 y la versión de tarifas 4.3 vigente, cuando el PAS cotiza de nuevo los mismos datos, entonces la cotización nueva indica «versión de tarifas 4.3» y su precio se calcula con esa versión, sin copiar el de la vencida |
| CA-11 | RF-09 · G7-13 | Dado una cotización del CB emitida el 02/11/2026 con precio $41.400 (versión 4.2), cuando el 06/11/2026 se publica la versión 4.3 y el PAS consulta esa cotización, entonces sigue mostrando $41.400 y «versión de tarifas 4.2».|
