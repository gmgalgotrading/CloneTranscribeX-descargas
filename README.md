# CloneTranscribeX

Graba y transcribe consultas y dictados **en tu propio Mac**. En **modo clínico** el audio nunca sale del ordenador: la transcripción se hace con inteligencia artificial instalada en el Mac, sin internet.

> **Aviso.** Es un prototipo, no un producto sanitario certificado. Revisa siempre el texto antes de copiarlo a una historia clínica.

### ⬇️ [Descargar CloneTranscribeX para Mac](https://github.com/gmgalgotrading/CloneTranscribeX-descargas/releases/latest/download/CloneTranscribeX.zip)

Solo Mac con chip Apple (M1 o posterior). Otras versiones en [Releases](https://github.com/gmgalgotrading/CloneTranscribeX-descargas/releases).

---

## Índice

- [Qué necesitas](#qué-necesitas)
- [Para médicos: instalar y usar](#para-médicos-instalar-y-usar)
- [Modo clínico](#modo-clínico)
- [Idiomas y motores](#idiomas-y-motores)
- [Motores en la nube (opcional, nunca con pacientes)](#motores-en-la-nube-opcional-nunca-con-pacientes)
- [Dónde se guardan los datos](#dónde-se-guardan-los-datos)
- [Problemas frecuentes](#problemas-frecuentes)

---

## Qué necesitas

| Requisito | Detalle |
|---|---|
| Ordenador | **Mac con chip Apple** (M1, M2, M3, M4 o posterior). No funciona en Mac con procesador Intel ni en Windows. |
| Sistema | **macOS 14.6 (Sonoma) o posterior**. Para comprobarlo:  → Acerca de este Mac. |
| Espacio libre | Unos **2 GB** para los modelos de transcripción, más el espacio de las grabaciones (1 hora ≈ 115 MB). |
| Internet | **Solo la primera vez**, para descargar los modelos. Después transcribe sin conexión. |
| Micrófono | El del Mac o uno externo. |

---

## Para médicos: instalar y usar

### 1. Instalar (una sola vez)

1. [Descarga **`CloneTranscribeX.zip`**](https://github.com/gmgalgotrading/CloneTranscribeX-descargas/releases/latest/download/CloneTranscribeX.zip). Se guarda en tu carpeta **Descargas**.

2. Haz doble clic en `CloneTranscribeX.zip`. Aparece la app **CloneTranscribeX**.
3. Arrástrala a la carpeta **Aplicaciones**. Si ya tenías una versión anterior, pulsa **Reemplazar**.
4. Ábrela con doble clic. La primera vez macOS avisa de que **no puede comprobar el desarrollador**: la app no está firmada por Apple. Es normal.
   1. Pulsa **Hecho** (u **OK**) en el aviso.
   2. Abre **Ajustes del Sistema → Privacidad y seguridad**.
   3. Baja hasta el mensaje sobre *CloneTranscribeX* y pulsa **Abrir igualmente**.
   4. Confirma con tu contraseña o Touch ID.

   No volverá a preguntar.

### 2. Permisos que pedirá

| Cuándo | Qué pide | Qué pulsar |
|---|---|---|
| La primera vez que pulses **Grabar** | Usar el micrófono | **Permitir** |
| La primera vez que uses **catalán o euskera** (motor Whisper) | Acceso a la carpeta Documentos, donde guarda ese modelo | **Permitir** |

### 3. Grabar y transcribir

1. Comprueba que arriba aparece la **franja verde «Modo clínico: solo motores locales»**.
2. Elige el **Idioma**.
3. Elige el **Motor**. Recomendado: **Parakeet**, el más rápido. Para catalán o euskera la app elige **Whisper** sola.
4. Pulsa **Grabar** (o ⌘R). Habla. Pulsa **Parar**.
5. Pulsa **Transcribir**.
   - **La primera vez** descarga el modelo (unos minutos, según tu conexión). Whisper además tarda alrededor de **1 minuto** en prepararse.
   - Después, unos pocos segundos.
6. Selecciona el texto, cópialo (⌘C) y pégalo donde lo necesites.

**En directo:** si activas **«En directo (Nemotron, local)»** antes de grabar, el texto aparece mientras hablas. Al pulsar **Parar** se muestra el texto final. Después puedes volver a pulsar **Transcribir** para pasar la misma grabación por otro motor. Funciona en todos los idiomas salvo catalán y euskera, y la primera vez tarda unos segundos en prepararse.

> **La transcripción no se guarda.** Solo se ve en pantalla. Cópiala antes de cerrar la app o de hacer otra grabación. El audio sí se guarda (ver [Dónde se guardan los datos](#dónde-se-guardan-los-datos)).

---

## Modo clínico

|  | **Modo clínico** (franja verde) | **Nube desbloqueada** (franja naranja) |
|---|---|---|
| Motores disponibles | Solo locales: Parakeet y Whisper | Locales + ElevenLabs y Mistral |
| ¿Sale el audio del Mac? | **Nunca** | Solo si eliges un motor de la nube |
| ¿Usar con pacientes? | **Sí** | **No** |

- La app **siempre se abre en modo clínico**.
- Para desbloquear la nube, pulsa **«Desbloquear nube…»** y confirma el aviso. Para volver, pulsa **«Volver a modo clínico»**.
- **Lo que grabes en modo clínico queda marcado para siempre como solo local.** Aunque luego desbloquees la nube, esa grabación no puede enviarse fuera del Mac. Verás un candado 🔒.
- No se puede cambiar de modo mientras grabas.

---

## Idiomas y motores

Primero eliges el idioma. La app solo te ofrece los motores que lo admiten.

| Idioma | Modo clínico (local) | Con la nube desbloqueada, además |
|---|---|---|
| Español, inglés, francés, alemán, italiano, portugués | Parakeet, Whisper | ElevenLabs, Mistral |
| Catalán | Whisper | ElevenLabs |
| Euskera | Whisper | — |
| Automático (la app detecta el idioma) | Parakeet, Whisper | ElevenLabs, Mistral |

| Motor | Dónde funciona | Notas |
|---|---|---|
| **Parakeet v3** | En el Mac | El más rápido. Recomendado por defecto. |
| **Whisper large-v3** | En el Mac | Necesario para catalán y euskera. La primera vez tarda alrededor de 1 minuto en prepararse. |
| **Nemotron Streaming** | En el Mac | Solo para el modo **En directo** (bloques de 560 ms). No admite catalán ni euskera. En sesiones muy largas puede poner menos signos de puntuación. |
| **ElevenLabs Scribe** | En la nube | Requiere clave y es de pago por uso. |
| **Mistral Voxtral** | En la nube | Requiere clave y es de pago por uso. |

---

## Motores en la nube (opcional, nunca con pacientes)

Pueden servir para contenido **sin pacientes**: congresos, cursos, vídeos, artículos o reuniones no clínicas. Necesitas una clave de cada servicio:

- **ElevenLabs:** crea una cuenta en elevenlabs.io y genera una *API key*.
- **Mistral:** crea una cuenta en console.mistral.ai y genera una *API key*.

Para añadirlas:

1. En la app, ve al menú **CloneTranscribeX → Ajustes…** (o pulsa **⌘,**).
2. Pega cada clave y pulsa **Guardar**. Debe aparecer **«Clave guardada ✓»**.

Las claves se guardan cifradas en el **Llavero de macOS**. La app nunca las muestra. Cada transcripción en la nube tiene un coste según la tarifa de cada servicio.

---

## Dónde se guardan los datos

| Qué | Dónde |
|---|---|
| Grabaciones (audio WAV) | `~/Library/Application Support/CloneTranscribeX/audio/` |
| Transcripciones | **No se guardan.** Solo están en pantalla. |
| Modelo Parakeet (~460 MB) | `~/Library/Application Support/FluidAudio/Models/` |
| Modelo Whisper (~600 MB) | `~/Documents/huggingface/` |
| Modelo Nemotron, en directo (~630 MB) | `~/Library/Application Support/FluidAudio/Models/nemotron-multilingual/` |
| Claves de la nube | Llavero de macOS |

Para abrir la carpeta de grabaciones:
1. En el Finder, ve al menú **Ir → Ir a la carpeta…**.
2. Pega la ruta y pulsa Intro.

**Protección de datos de pacientes:**
- Activa **FileVault** (Ajustes del Sistema → Privacidad y seguridad → FileVault) para que el disco esté cifrado.
- Borra las grabaciones cuando ya no las necesites.
- No uses los motores en la nube con pacientes.

---

## Problemas frecuentes

| Mensaje o situación | Solución |
|---|---|
| «No se puede abrir… Apple no puede comprobar…» | Ajustes del Sistema → Privacidad y seguridad → **Abrir igualmente** (ver [Instalar](#1-instalar-una-sola-vez)). |
| «Sin permiso de micrófono» | Ajustes del Sistema → Privacidad y seguridad → **Micrófono** → activa CloneTranscribeX. Cierra y abre la app. |
| La primera transcripción tarda mucho | Normal: está descargando o preparando el modelo. Las siguientes van rápido. |
| Error al transcribir la primera vez | Comprueba la conexión a internet: hace falta para descargar el modelo. |
| «Falta la clave de…» | Añádela en **Ajustes (⌘,)**. Solo afecta a los motores en la nube. |
| «… no admite …» | Ese motor no tiene ese idioma. Elige otro motor en la lista. |
| El interruptor «En directo» está gris | Estás grabando, o el idioma es catalán o euskera (Nemotron no los admite). |
| No aparecen ElevenLabs ni Mistral | Estás en modo clínico, que es lo correcto con pacientes. Para otros usos, pulsa «Desbloquear nube…». |

---

## Sobre este repositorio

- Aquí solo se publica la **app ya compilada** y estas instrucciones. El código fuente es privado.
- **Proyecto independiente**, sin relación con TranscribeX ni con sus autores.
- Para comprobar que la descarga no se ha alterado, cada versión indica el código SHA-256 del archivo.
