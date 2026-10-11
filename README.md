# Planta — Estudio de planos

Editor de planos en planta con Canvas 2D, controles táctiles y funcionamiento como PWA. Aplicación estática sin dependencias ni proceso de compilación.

## Funciones

- Cuadrícula automática de 100, 10, 1 y 0,1 cm según el zoom, o separación manual.
- Dibujo de líneas con ajuste a puntos y medidas en centímetros.
- Modo Editar: mover elementos, cambiar estilos y definir la longitud de una línea manteniendo fijo el extremo izquierdo (el superior en líneas verticales).
- Modo Extremos: desplazar un único punto de una línea sin trasladar el segmento completo.
- Biblioteca de muebles, puertas, ventanas, sanitarios y plantas; tamaño y giro editables.
- Deshacer y rehacer; guardado automático en el navegador.
- Importación y exportación de proyectos JSON; exportación del plano completo a PNG y PDF.
- Manifest y service worker para instalación y uso sin conexión tras cargar los recursos.

## Ejecutar en local

Con Python 3, desde la raíz del repositorio:

```sh
python -m http.server 8000 --directory dist
```

Abrir http://localhost:8000. Para el despliegue, servir el contenido de `dist/` en la raíz de un dominio HTTPS. Las rutas de la PWA son absolutas; un despliegue bajo un subdirectorio requiere adaptarlas.

## Archivos

- `dist/index.html`: interfaz.
- `dist/style.css`: diseño adaptable.
- `dist/app.js`: editor, almacenamiento y exportaciones.
- `dist/manifest.webmanifest`: configuración de la PWA.
- `dist/sw.js`: caché sin conexión; incrementar su versión al cambiar recursos.

## Datos y límites

Los planos se guardan en el almacenamiento local del navegador, no en un servidor. Exportar JSON permite conservar copias independientes o trasladarlas a otro equipo. El PDF contiene una imagen del plano, no geometría vectorial ni una escala de impresión garantizada. Es una herramienta de dibujo, no una validación técnica de un proyecto arquitectónico.

## Atajos

- `V`: editar.
- `P`: editar extremos.
- `L`: dibujar línea.
- `H`: mover vista.
- `Ctrl/Cmd + Z`: deshacer; añadir `Shift` para rehacer.
- `Supr`: eliminar la selección.
- `Esc`: cancelar la selección.
