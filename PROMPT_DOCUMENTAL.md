# Prompt maestro: documental de reguetón (10 min) + 3 Shorts

Pégalo en una sesión de Claude Code abierta en tu PC (carpeta de trabajo `D:\clude`), con la skill `editor-video-retencion` y Remotion instalados. Adjunta el guion del personaje.

---

Eres mi editor y productor de documentales para YouTube. Con el guion que te adjunto, produce un documental de unos 10 minutos en 1920x1080 a 30 fps y 3 Shorts verticales (1080x1920) que lleven al vídeo principal. Todo se hace con Remotion. Trabaja en la carpeta del proyecto y no pidas confirmación en pasos intermedios; solo detente antes de subir nada.

## 1. Preparación
1. Divide el guion en escenas y guárdalas en `scenes.json`: texto de la narración, duración estimada, imágenes o vídeos necesarios, texto en pantalla y animación.
2. Haz una lista de todas las personas, lugares, discos, canciones y cifras que se mencionan. Cada una va a tener su propio recurso visual.

## 2. Regla principal: cada personaje mencionado se tiene que ver
- La primera vez que se nombra a alguien, su imagen aparece en pantalla dentro del primer segundo de decir su nombre, con un rótulo inferior (nombre y rol).
- Si el personaje se menciona de nuevo más de 30 segundos después, vuelve a aparecer su imagen.
- Fuentes de imágenes, por orden de preferencia:
  1. Wikimedia Commons y otras con licencia libre (CC0, CC BY, CC BY-SA). Guarda autor, licencia y enlace.
  2. Material de prensa oficial y fotos de archivo con licencia.
  3. Capturas de titulares y artículos citados, pequeñas y con comentario encima (uso legítimo). Marca cada una para que yo la revise.
  4. Si no hay imagen utilizable: ilustración estilizada o silueta con el nombre. Nunca generes con IA el rostro de una persona real y lo presentes como foto real.
- Crea `assets/manifest.json`: para cada recurso, archivo local, URL de origen, autor, licencia, texto de atribución y minuto en que se usa. Si no consigues una licencia clara, marca `"revisar": true`.

## 3. Audio
- Sin música comercial. Solo música de la biblioteca de audio de YouTube, CC0 o generada, con la licencia anotada en el manifiesto.
- Efectos de sonido solo CC0 o libres.
- Locución: usa el audio que yo te dé; si no hay, genera una voz con la herramienta que tengamos configurada. Mide la duración real de cada frase y ajusta las escenas a ella.
- Mezcla: voz a -14 LUFS aproximados, música 18 dB por debajo de la voz y con ducking.

## 4. Animaciones en Remotion
Componentes reutilizables:
- `LowerThird` (nombre y rol del personaje).
- `PhotoKenBurns` (zoom y desplazamiento lento sobre una foto).
- `Timeline` (años en una línea de tiempo que se va dibujando).
- `StatCounter` (cifras que suben: ventas, entradas, puestos en listas).
- `HeadlineCard` (titular de prensa con la fuente visible).
- `QuoteCard` (cita textual con el nombre de quien la dijo).
- `ChapterTitle` (título de capítulo).
- `Captions` (subtítulos palabra por palabra, sincronizados con la voz).
Reglas de ritmo: un cambio visual cada 4 a 7 segundos, el gancho en los primeros 5 segundos, sin tiempos muertos, transiciones suaves y coherentes, tipografía legible en móvil.

## 5. Control de calidad antes de renderizar
Comprueba y corrige hasta que todo cumpla:
- Cada personaje nombrado tiene su imagen en pantalla.
- Ninguna imagen sin licencia o sin atribución en el manifiesto.
- Sin música con copyright.
- Sin fotogramas negros ni imágenes estiradas.
- Subtítulos dentro de la zona segura y legibles.
- Duración total entre 9:30 y 10:30.
Después renderiza y guarda en `/salida`. Genera también una miniatura de 1280x720.

## 6. Paquete para YouTube (`youtube.md`)
- 3 opciones de título (máx. 60 caracteres), sin engaños.
- Descripción: resumen de 2 líneas, capítulos con tiempos, fuentes consultadas, créditos de imágenes y de audio, y la divulgación de contenido alterado o sintético si se usó voz generada o ilustraciones por IA.
- Etiquetas y texto de la miniatura.
- 3 Shorts de 30 a 45 segundos, cada uno con un ángulo distinto del documental (un dato, un conflicto, una cita). Cada uno tiene gancho, cierre con "El documental completo está en mi canal" y el vídeo principal enlazado como vídeo relacionado, más un comentario fijado con el enlace.

## 6b. Subida
- Sube todo como **privado** con la extensión de Claude en Chrome, usando el canal que yo indique.
- No lo publiques. Dame el enlace para revisarlo y yo lo publico.

Al terminar, devuélveme: rutas de los archivos, lista de recursos marcados como `revisar`, y cualquier duda sobre licencias.
