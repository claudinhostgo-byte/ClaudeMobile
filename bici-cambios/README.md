# Los cambios de la bici

Animación (30 s): https://claude.ai/artifact/68tDdVLqKy4tsPrYqMuNRF

`voz-narracion.mp3` es la voz que explica cada parte, ya calzada con los tiempos del video
(dura 30 s y empieza en 0:00). Se generó con Kokoro, un modelo de voz gratuito y de código abierto.

## Cómo juntar la voz con el video

1. En la página de la animación, usa **Export** y guarda el video en MP4.
2. Abre un editor (Clipchamp, CapCut o similar), pon el MP4 y agrega `voz-narracion.mp3` en el segundo 0:00.
3. Si quieres, baja un poco el volumen de la música del video.

O desde la terminal con ffmpeg:

```
ffmpeg -i video.mp4 -i voz-narracion.mp3 -filter_complex "[0:a]volume=0.35[m];[m][1:a]amix=inputs=2:duration=first[a]" -map 0:v -map "[a]" -c:v copy video-con-voz.mp4
```

## Guion

| Tiempo | Parte | Voz |
|---|---|---|
| 0–3,5 s | La bici | ¿Sabías que tu bici tiene un truco secreto? ¡Los cambios! |
| 3,5–9,5 s | La cadena | Cuando pedaleas, giras el plato. La cadena tira del piñón de atrás… ¡y la rueda gira! |
| 9,5–15,5 s | Piñón grande | Con el piñón grande, una vuelta de pedal es una vuelta de rueda. Es suavecito: ¡perfecto para subir cerros! |
| 15,5–21,5 s | Piñón chico | Con el piñón chico cuesta más, pero una vuelta de pedal, ¡son tres vueltas de rueda! Vas rapidísimo. |
| 21,5–26,5 s | El cambio | Cuando aprietas la palanca, ¡clic!, la cadena salta a otro piñón. |
| 26,5–30 s | Final | Para subir, piñón grande. Para ir rápido, piñón chico. ¡A pedalear! |
