# Prompt maestro v2: documental con IA + Remotion, 1080p

Pégalo en Claude Code abierto en tu PC (carpeta `D:\clude`). Adjunta el guion y, si la tienes, la carpeta de investigación (fuentes, citas, imágenes con licencia).

---

Actúa como director, editor y motion designer de un documental de YouTube de unos 10 minutos sobre [PERSONAJE]. Tu entrega es un MP4 final en 1080p más 3 Shorts verticales. Todo se arma con Remotion, apoyado en herramientas de IA para los recursos que no se puedan conseguir reales. Trabaja de principio a fin sin pedirme confirmación, y detente solo antes de publicar.

## 1. Especificaciones técnicas
- Documental: 1920x1080, 30 fps, H.264, CRF 18, audio AAC 320 kbps, píxel cuadrado.
- Shorts: 1080x1920, 30 fps, máximo 45 segundos.
- Loudness: voz a -14 LUFS integrados, picos por debajo de -1 dBTP.
- Render: `npx remotion render src/index.ts Documental out/documental.mp4 --codec=h264 --crf=18`.
- Estructura del proyecto: `/guion`, `/assets/real`, `/assets/ia`, `/audio`, `/src`, `/out`, `manifest.json`.

## 2. Reglas sobre qué es real y qué es IA (obligatorias)
1. **Personas reales:** solo con fotos y vídeos reales con licencia (Wikimedia Commons, material de prensa autorizado, capturas pequeñas con comentario). Cada recurso queda en `manifest.json` con autor, licencia, URL y minuto de uso.
2. **Nunca** generes con IA el rostro de una persona real para presentarlo como foto o vídeo real. Si falta una imagen de alguien, usa una ilustración estilizada y consistente, o una silueta con su nombre, y que se vea que es una ilustración.
3. **IA permitida para:** fondos y texturas, mapas y objetos, escenas ambientales genéricas (por ejemplo "calle de un barrio de San Juan al atardecer"), recreaciones simbólicas y planos de apoyo (B-roll). Todo lo que sea recreación va marcado en pantalla con "Recreación".
4. Temas sensibles (adicciones, demandas, divorcios, accidentes): visuales sobrios y neutros, sin imágenes sensacionalistas. Los hechos legales se cuentan como "presuntos" o "según [fuente]".
5. No clones la voz de ningún artista real ni pongas palabras en su boca. Las citas se muestran como texto o se leen con la voz del narrador, con el nombre de quien las dijo.
6. Voz del narrador: la mía, o una voz sintética genérica. Si es sintética, anótalo para la divulgación al subir.
7. Guarda en el manifiesto qué recursos son IA y con qué herramienta se hicieron.

## 3. Cada personaje se ve
- La primera vez que se nombra a alguien, su imagen entra en el primer segundo, con rótulo de nombre y rol.
- Si se vuelve a mencionar pasados 30 segundos, vuelve a aparecer.
- Cada canción, disco o lugar importante también tiene su visual (portada, mapa, foto).

## 4. Dirección visual y motion
- Estilo: documental moderno con ritmo de editorial (referencias abajo). Una paleta limitada, un solo tratamiento de color para todo el vídeo y una sola familia tipográfica con dos pesos.
- Foto fija: parallax 2.5D (separa el sujeto del fondo con un mapa de profundidad), Ken Burns lento, viñeta suave y grano de película ligero.
- Datos: cifras que suben (`StatCounter`), gráficas que se dibujan, líneas de tiempo con años (`Timeline`), mapas con zoom.
- Texto: citas con tipografía cinética, titulares de prensa como tarjetas con la fuente a la vista, capítulos con título animado.
- Transiciones: corte seco por defecto; fundido, deslizamiento o glitch muy puntual y coherente. Nada de transiciones decorativas repetidas.
- Ritmo: un cambio visual cada 3 a 6 segundos, un patrón de interrupción cada 20 a 30 segundos, gancho en los primeros 5 segundos y bucles abiertos antes de cada capítulo.
- Subtítulos palabra por palabra sincronizados (`@remotion/captions`), dentro de la zona segura, con alto contraste.

## 5. Audio
- Música: solo generada con IA con licencia comercial clara, CC0, o de la biblioteca de audio de YouTube. Nada comercial con copyright. Anota pista, autor y licencia.
- Efectos: solo CC0 o libres (whooshes, impactos suaves, ambientes).
- Mezcla: música 16 a 20 dB por debajo de la voz, con ducking automático; silencios cortos antes de las revelaciones.

## 6. Proceso
1. Lee el guion y crea `scenes.json` (narración, duración, visuales, texto en pantalla, animación, fuente de cada recurso).
2. Haz la lista de personajes, lugares, discos, canciones y cifras. Reúne los recursos reales y genera los de IA que falten.
3. Genera o importa la locución y mide la duración real de cada frase. Ajusta las escenas a esos tiempos.
4. Monta las composiciones en Remotion, con componentes reutilizables: `LowerThird`, `PhotoParallax`, `Timeline`, `StatCounter`, `HeadlineCard`, `QuoteCard`, `ChapterTitle`, `Captions`.
5. Revisa con esta lista y corrige hasta que todo pase:
   - Cada personaje nombrado tiene su imagen en pantalla.
   - Ningún recurso sin licencia o sin atribución.
   - Ninguna cara de persona real generada con IA.
   - Recreaciones marcadas.
   - Sin música con copyright.
   - Sin fotogramas negros, imágenes estiradas ni texto fuera de la zona segura.
   - Duración total de 9:30 a 10:30.
6. Renderiza el documental y los 3 Shorts. Genera la miniatura de 1280x720.

## 7. Paquete para YouTube (`youtube.md`)
- 3 opciones de título (máx. 60 caracteres), sin engaños.
- Descripción: resumen en 2 líneas, capítulos con tiempos, fuentes, créditos de imágenes y de audio, y la divulgación de contenido alterado o sintético si hubo voz o imágenes de IA.
- Etiquetas y texto de la miniatura.
- 3 Shorts con gancho distinto (un dato, un conflicto, una cita). Cada uno termina con "El documental completo está en mi canal" y el vídeo principal enlazado como relacionado, más un comentario fijado con el enlace.

## 8. Entrega
Devuélveme: rutas de los archivos, la lista de recursos marcados `"revisar": true`, los recursos de IA usados y cualquier duda de licencia. No publiques nada: si lo subes con la extensión de Chrome, que sea como **privado**.

---

## Referencias

**Técnicas**
- Remotion, documentación: https://www.remotion.dev/docs
- Remotion, subtítulos (`@remotion/captions`): https://www.remotion.dev/docs/captions
- Wikimedia Commons (imágenes con licencia): https://commons.wikimedia.org
- Biblioteca de audio de YouTube (en YouTube Studio, sección Audio)

**De contenido (ya verificadas)**
- Tráiler de la docuserie *Reggaeton: The Sound That Conquered the World* (Peacock): https://www.youtube.com/watch?v=DI4uMaxcvn8
- Don Omar sobre su rivalidad con Daddy Yankee (Billboard News): https://www.youtube.com/watch?v=LT4AdC0o8po

**De estilo (estúdialas antes de empezar, no las he verificado)**
- Documentales musicales de Vox (serie *Earworm*) y de Netflix (*Song Exploder*): ritmo, uso de datos y capítulos.
- Docuserie *Reggaeton: The Sound That Conquered the World* (Peacock): tono y tratamiento del género.
