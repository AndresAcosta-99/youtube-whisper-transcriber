# YouTube Transcriptor con Whisper

Descarga videos de YouTube y genera transcripciones automáticas en español con timestamps usando Whisper de OpenAI.

## Requisitos

- Python 3.8+
- FFmpeg

### Instalación

```bash
# Instalar dependencias
pip install yt-dlp openai-whisper torch pandas python-docx

# Instalar FFmpeg
# macOS:
brew install ffmpeg

# Linux:
sudo apt install ffmpeg
```

## Uso

**Un video:**
```bash
python youtube_transcriptor.py
```

**Múltiples videos (CSV):**
```bash
python youtube_transcriptor.py videos.csv
```

Formato del CSV:
```csv
url
https://www.youtube.com/watch?v=ejemplo1
https://www.youtube.com/watch?v=ejemplo2
```

## Funcionamiento

1. Descarga el audio del video con yt-dlp
2. Convierte a WAV mono 16kHz con FFmpeg
3. Transcribe con Whisper (modelo medium)
4. Genera documento Word con timestamps
5. Registra metadatos en CSV
6. Limpia archivos temporales

## Salida

**Transcripción (.docx):**
```
Transcripción de Audio

[00:00 → 00:05] Bienvenidos a esta conferencia sobre inteligencia artificial.
[00:05 → 00:12] Hoy vamos a hablar sobre los avances más recientes.
```

**Log (transcriptions_log.csv):**
- title, upload_date, duration, view_count, channel, URL, status

## GPU

El script detecta automáticamente GPU NVIDIA con CUDA para acelerar la transcripción. Funciona también en CPU.

---

# YouTube Transcriptor with Whisper

Downloads YouTube videos and generates automatic Spanish transcriptions with timestamps using OpenAI's Whisper.

## Requirements

- Python 3.8+
- FFmpeg

### Installation

```bash
# Install dependencies
pip install yt-dlp openai-whisper torch pandas python-docx

# Install FFmpeg
# macOS:
brew install ffmpeg

# Linux:
sudo apt install ffmpeg
```

## Usage

**Single video:**
```bash
python youtube_transcriptor.py
```

**Multiple videos (CSV):**
```bash
python youtube_transcriptor.py videos.csv
```

CSV format:
```csv
url
https://www.youtube.com/watch?v=example1
https://www.youtube.com/watch?v=example2
```

## How it works

1. Downloads video audio with yt-dlp
2. Converts to mono 16kHz WAV with FFmpeg
3. Transcribes with Whisper (medium model)
4. Generates Word document with timestamps
5. Logs metadata to CSV
6. Cleans temporary files

## Output

**Transcription (.docx):**
```
Transcripción de Audio

[00:00 → 00:05] Welcome to this conference on artificial intelligence.
[00:05 → 00:12] Today we will talk about the latest advances.
```

**Log (transcriptions_log.csv):**
- title, upload_date, duration, view_count, channel, URL, status

## GPU

Script automatically detects NVIDIA GPU with CUDA to accelerate transcription. Also works on CPU.

## License

MIT
