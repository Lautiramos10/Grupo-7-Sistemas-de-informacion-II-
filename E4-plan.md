# Plan que se siguió para la página v2 (E4)

1. **Se mantiene lo de la v1** (UC-01 pasos 1 a 5, RF-01, RF-03, RF-04): formulario, tarifas
   4.2, cálculo como función pura, avisos de RF-05 y de la antigüedad del vehículo.
2. **RF-02 v2.** El registro guarda y muestra la *fecha de emisión* (solo la fecha, sin hora).
3. **RF-06 (validez).** Menos de 15 días corridos desde la emisión es «vigente»; más de 15,
   «vencida». *Decisión:* el día quince exacto no se da por vigente ni por vencida, porque el
   acta no lo dice: se muestra como «pendiente de decisión (M. Duarte)».
4. **RF-07 (no aceptar una vencida).** Cada fila del registro tiene un botón «Aceptar» que se
   bloquea si la cotización está vencida (o en el día quince) y muestra el aviso al PAS.
   *Decisión:* la especificación no tiene un caso de uso para aceptar; el botón existe solo para
   poder ejecutar RF-07 (CA-09).
5. **RF-08 (la nueva no hereda el precio).** Cotizar siempre calcula con la tarifa vigente y los
   datos del formulario; nunca copia el precio de otra cotización. *Decisión:* no hay botón de
   «volver a cotizar con un solo paso», porque ese punto sigue abierto (Acta 3.ª §4.1).
6. **RF-09 (conserva su precio).** El precio y la versión se guardan al cotizar y no se
   recalculan al mostrar el registro. *Límite:* como la especificación no tiene dónde publicar
   una versión de tarifas nueva, la página solo conoce la 4.2 y no se puede probar el cambio de
   tarifa (CA-04, segunda parte, CA-10 y CA-11 no son ejecutables).
7. **Control de prueba: «Fecha de hoy».** *Decisión:* un campo de fecha que hace de reloj de la
   página (fecha de emisión de las cotizaciones nuevas y de la consulta de vigencia), para
   probar CA-08 y CA-09 sin esperar quince días. Está marcado como control de prueba y no sale
   de ningún requerimiento. Con él, el año de hoy también define la antigüedad del vehículo.
8. **Cotización aceptada.** *Decisión:* la especificación no dice qué pasa con una cotización
   aceptada cuando pasan los quince días; se muestra como «Aceptada» y no se le recalcula la
   vigencia.
9. **RF-10 (antigüedad máxima)** Un vehículo de más de 20 años no se cotiza: se muestra el aviso y no se calcula ni se registra precio.
10. **Preguntas para el grupo:** ¿el día quince cuenta como vigente? ¿una cotización aceptada
   puede vencer? ¿el control de fecha de hoy es aceptable como evidencia?
