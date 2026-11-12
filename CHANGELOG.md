# Registro de cambios de ATEMPO

## 0.16.0 — 2026-11-12

Detalle en los eventos y alarmas que empiezan a sonar más pronto.

### Novedades
- Detalle de los eventos: cada evento puede tener un detalle opcional de varias líneas (hasta 500 caracteres) en «Ver más». Si el evento ya tiene detalle, «Ver más» se abre solo. En la agenda del día se muestra recortado y solo si existe.

### Mejoras
- El sonido de la alarma comienza antes: ATEMPO comprueba que la alarma siga vigente, la hace sonar y solo después programa la siguiente y guarda el historial (antes todo eso ocurría antes del sonido).
- ATEMPO mide internamente cuánto tarda cada alarma en sonar respecto de su hora, para poder diagnosticar retrasos. No hay pantalla ni nada que configurar.

## 0.15.0 — 2026-11-09

Estado del sistema más preciso y aviso 5 minutos antes de cada alarma.

### Novedades
- Aviso previo: 5 minutos antes de que suene una alarma aparece la notificación «¡Tu alarma está por sonar!» con su nombre, la hora real y una cuenta regresiva. También funciona con las alarmas pospuestas (se calcula con la nueva hora). Es silenciosa para no despertarte antes de tiempo y se puede desactivar en cada alarma, en «Más opciones» › «Aviso previo».
- Logo de ATEMPO en Inicio, junto al nombre.

### Correcciones
- Alarmas exactas: ATEMPO ya no dice «Habilitado» cuando «Alarmas y recordatorios» está desactivado. En Android 12, si la batería de ATEMPO está «Sin restricciones», Android igual permite alarmas exactas; ahora se indica así, con la recomendación de activar el permiso. Si no hay permiso ni exención, se marca como crítico (Android podía retrasar la alarma hasta una hora).
- Volumen de alarmas: se evalúa en porcentaje del máximo de tu teléfono y advierte si está bajo (menos de 20 %) o en el mínimo, también en teléfonos que no permiten bajarlo a 0. Muestra el porcentaje y abre el control de volumen.
- Batería: un solo indicador con los mismos estados que muestra Android («Sin restricciones», «Optimizado», «Restringido»), sin indicadores que se contradigan.

### Mejoras
- Nuevo indicador informativo «Bloqueo de pantalla» que explica que no es necesario para que las alarmas suenen.
- «Usar los colores de tu fondo de pantalla» explica lo que hace (Material You) y ahora también colorea la tarjeta principal de Inicio. Solo aparece en Android 12 o superior.

## 0.14.0 — 2026-11-08

Ahora puedes cancelar una alarma pospuesta sin desactivarla para los días siguientes.

### Novedades
- Cancelar postergación: mientras una alarma está pospuesta aparece un aviso silencioso «Trabajo · Pospuesta · Volverá a sonar a las 7:10 a. m.» con el botón «Cancelar postergación», que funciona aunque la app esté cerrada.
- La misma opción está en el detalle de la alarma, en la tarjeta de la próxima alarma en Inicio y en el menú de la alarma en la lista de Alarmas (que ahora indica «Pospuesta · volverá a sonar a las…»).
- Solo se cancela esa repetición: la alarma sigue activada y vuelve a sonar normalmente la próxima vez. Una alarma de una sola vez queda terminada, igual que al detenerla.

### Mejoras
- El historial de la alarma indica «Cancelaste la postergación».
- Cancelar la postergación cuenta como alarma atendida en los logros, pero no como detenida «sin posponer».

## 0.13.0 — 2026-11-08

Correcciones importantes en alarmas y avisos para los eventos del calendario.

### Novedades
- Avisos de eventos del calendario: notificación el día del evento a las 6:00 a. m. (hora editable y se puede desactivar). Las fechas especiales se avisan cada año; las vacaciones, el primer día. Al tocar el aviso se abre el evento.
- Selector de tipo de evento en tarjetas con ícono, color y el nombre completo; descripción, repetición anual y aviso pasan a «Ver más».

### Correcciones
- Eliminar una alarma desde su detalle ya no deja la pantalla en negro: vuelve a la pantalla de la que venías y quita también su programación.
- Las alarmas rápidas suenan exactamente a los minutos elegidos: «+5 min» ya no dice ni programa 6 minutos.
- El tiempo restante de la próxima alarma en Inicio se calcula con la hora real (no con un minuto de más).
- Después de abrir un evento desde su notificación, «Inicio» en la barra inferior vuelve a funcionar, y al regresar al Calendario el evento no se vuelve a abrir.
- Una alarma pospuesta y luego detenida ya no cuenta para el logro «Sin posponer».
- Estado del sistema: «Optimización de batería» indica «Desactivada para ATEMPO» en vez de un confuso «Habilitado».
- En el formulario de eventos, con «Ver más» abierto, el contenido se desplaza y la descripción ya no queda fuera de la pantalla.

### Mejoras
- Al crear una alarma, la hora inicial es la siguiente en múltiplos de 5 minutos (3:37 → 3:40).
- Estado del sistema más claro: grupos «Configuración automática» y «Configuración manual», con indicadores de check, alerta o pendiente. Se quitaron el diagnóstico técnico y la guía del fabricante.

## 0.12.0 — 2026-11-08

Logros que se adaptan a ti, un inicio automático que se comprueba solo y un Inicio más limpio.

### Novedades
- Logros dinámicos: hasta 5 objetivos a la vez según lo que haces de verdad (tareas, alarmas atendidas, puntualidad, constancia, tomas, retos y calendario). Al completar uno pasa a «Completados» y aparece el siguiente, con una dificultad que crece poco a poco.
- Pantalla de Logros con progreso animado, nivel y categoría, y el detalle de cada logro: objetivo exacto, qué cuenta y desde cuándo.
- Celebración al desbloquear un logro y notificación opcional. Se activan o desactivan en Configuración; desactivarlos no borra lo conseguido.
- Acceso directo a Logros (trofeo) junto al engranaje en Inicio.
- Diagnóstico interno en Estado del sistema: ATEMPO comprueba en silencio, sin crear alarmas ni hacer ruido, si Android la despierta con la app cerrada y si recupera las alarmas tras reiniciar.

### Correcciones
- La lista de próximas alarmas de Inicio ya no se salta la siguiente ejecución: una alarma diaria muestra mañana antes que pasado mañana, en orden real e incluyendo las postergaciones.

### Mejoras
- Inicio automático con estados claros: Verificado, Pendiente de verificación, Confirmación manual, No configurado o No disponible. Al volver de su ajuste puedes indicar si ya está activado.
- Se retiró «Probar alarma»: ya no hace falta programar una alarma para comprobarlo.
- Actualizaciones muestra siempre la última versión publicada y sus novedades al entrar, también sin conexión (con la fecha de la última consulta). «Verificar nuevamente» queda como acción secundaria y «Actualizar» como la principal.
- Inicio más limpio: sin los contadores de alarmas ni «Ver todas» en tareas.
- Detalle de alarmas recurrentes: las cuatro acciones en una cuadrícula compacta, con una explicación breve y su estado (pausada hasta, fechas excluidas...).

## 0.11.0 — 2026-11-08

Alarmas más fiables y un historial que explica qué pasó con cada una.

### Novedades
- Historial con motivo: «No sonó» indica por qué (teléfono apagado, app detenida, ahorro de energía, permisos...) y si es un hecho comprobado o una causa probable. También registra las omisiones a propósito (pausa, fecha excluida, desactivada) y los cambios al editar, con el valor anterior y el nuevo.
- «Probar alarma» en Estado del sistema: una alarma real en 1–2 minutos para comprobar que suena con la app cerrada.
- Punto rojo en el engranaje y estado «Completo / Incompleto» cuando falta algo que puede impedir que las alarmas suenen; aviso antes de guardar o activar en ese caso.
- Todas las opciones de Estado del sistema se pueden abrir, también las que están en verde, incluido «Inicio automático» con instrucciones según el fabricante.

### Correcciones
- Una alarma que Android entrega tarde (por ejemplo, retenida por el ahorro de energía del fabricante) ahora **suena** hasta una hora después, en lugar de marcarse como «No sonó».
- Desactivar una alarma pospuesta cancela la postergación de inmediato: no vuelve a sonar, ni con la app cerrada ni tras reiniciar.
- Una alarma de una sola vez sigue activa mientras está pospuesta y se desactiva sola al terminar.
- Si el volumen de alarmas del teléfono está en cero, ATEMPO lo sube mientras suena y luego lo restaura.

### Mejoras
- Las alarmas nuevas empiezan en «Una vez»; las exclusiones solo aparecen en alarmas que se repiten.
- Al guardar, los cambios se aplican desde ese momento (ya no se pregunta desde cuándo) y la alarma queda activada.
- Volumen progresivo solo con volumen mayor al 50 %.
- Detalle más compacto: secciones que se abren y cierran, máximo 5 filas con «Ver más», la postergación pendiente aparece en «Próximas ocurrencias» y las acciones de repetición no se muestran en alarmas de una sola vez.

## 0.10.0 — 2026-11-07

Primera versión con actualizaciones integradas: ATEMPO comprueba, descarga y verifica las versiones oficiales sin necesidad de conectar el teléfono al ordenador.

### Novedades
- Nueva sección «Actualizaciones» en Configuración: versión instalada, canal, última comprobación y botón «Verificar actualizaciones».
- Comprobación automática en segundo plano al abrir la app, con aviso opcional cuando hay una versión nueva.
- Descarga con progreso y opción de cancelar; la instalación la confirma siempre Android.
- Verificación de cada actualización antes de instalarla: huella SHA-256 publicada en metadatos firmados y certificado oficial del desarrollador.

### Mejoras
- Indicador en Configuración (y en el engranaje de la barra superior) cuando hay una actualización disponible.
