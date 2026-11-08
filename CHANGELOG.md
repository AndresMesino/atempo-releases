# Registro de cambios de ATEMPO

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
