
# 🎙️ QalamAI Speech Translator — Modular AI Speech Translation Suite

A **multi-module monorepo** for complete speech translation workflows — from environment validation and dataset preparation to batch translation, realtime OTT/YouTube streaming, and a full-featured Flask web UI.

---

## 🧭 Repository Overview

| Module       | Folder                       | Purpose                              |
| ------------ | ---------------------------- | ------------------------------------ |
| **Module 1** | `speech-translator/module1/` | Environment setup and sanity checks  |
| **Module 2** | `speech-translator/module2/` | Offline / batch translation toolkit  |
| **Module 3** | `speech-translator/module3/` | OTT-style realtime translation (CLI) |
| **Module 4** | `speech-translator/module4/` | Flask web UI (mic, upload, YouTube)  |

---

## 🚀 Module Details

### 🧩 Module 1 — Environment & Stack Check

* Quick verification of Python, audio, and GPU libraries
* Sanity tests for STT and translation components
* Ideal for first-time setup or CI pipelines
  **Files:** `colab_setup.ipynb`, `test_env.py`, `requirements.txt`

---

### 🗂️ Module 2 — Offline & Batch Translation Tools

* Download / prepare datasets (e.g., from Hugging Face)
* Convert audio formats (`mp3 ↔ wav`) with 16kHz mono normalization
* Perform batch STT → translate → TTS
* Stores outputs, logs, and metadata
  **Folders:** `data/`, `outputs/`, `logs/`
  **Goal:** Efficient dataset-based translation workflows

---

### 🔴 Module 3 — OTT / Realtime Translation (Scripted)

* CLI-based realtime translator from **microphone or stream inputs**
* Suitable for rapid experimentation without a server or UI
* Can simulate OTT captioning or live subtitle generation
  **Script:** `module3_ott_realtime.py`

---

### 🌐 Module 4 — Flask Web App (Interactive UI)

* Intuitive web interface supporting:

  * 🎤 Live microphone translation
  * 📁 Audio/video file uploads with playback and TTS
  * ▶️ YouTube translation via audio chunking (~8s)
* **STT:** Google SpeechRecognition (multi-pipeline with fallbacks)
* **TTS:** Edge TTS (gendered voices) → fallback to gTTS
* **Robustness:** Automatic fallback conversion (moviepy → ffmpeg → librosa → pydub)

**Supported languages:**
`en`, `hi`, `pa`, `mr`, `kn`, `te`, `ta`, `gu`, `ml`, `bn`, `or`, `ur`

---

## 🧰 Prerequisites

* **Python:** 3.11 – 3.13
* **FFmpeg:**

  * Windows: auto-handled via `imageio_ffmpeg` in Module 4
  * Otherwise: install manually and add to `PATH`
  * Download: [https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)
* **YouTube Support:** requires `pytube` or `yt-dlp`

---

## ⚡ Quick Start — Module 4 (Flask Web App)

```bash
cd speech-translator/module4
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python app.py
```

Open your browser:

```
http://127.0.0.1:5000
```

> 💡 If deploying front-end separately (e.g., Netlify),
> update `window.BACKEND_BASE_URL` in `index.html` to point to your Flask backend URL.

---

## 🧪 Module 2 — Batch Translation Usage

Convert files, batch translate, and manage datasets:

```bash
# Convert MP3 to WAV
python convert_mp3_to_wav.py

# Run batch translator
python module2_batch_translator.py

# Fetch sample datasets
python fetch_audio_datasets.py
```

Refer to `QUICK_START.md` and module-specific `README.md` for details.

---

## 🎧 Module 3 — OTT / Realtime Script Usage

Run the standalone OTT realtime translator:

```bash
python module3_ott_realtime.py
```

Configuration and quick examples are provided in
`speech-translator/module3/README.md` and `QUICK_START.md`.

---

## ⚙️ Configuration Notes

* **STT Language Hint:**
  `/mic_record` supports `source_lang` hints for better accuracy.
* **Audio Conversion Chain:**
  Automatic pipeline tries: `moviepy → ffmpeg → librosa → pydub`.
* **YouTube Failover:**
  Falls back to `yt-dlp` if `pytube` fails.

---

## 🧩 Troubleshooting

| Issue                            | Cause / Fix                                                          |
| -------------------------------- | -------------------------------------------------------------------- |
| **FFmpeg not found**             | Install FFmpeg and verify `ffmpeg -version` works                    |
| **400/500 API error**            | Check Flask logs; often caused by invalid URL or STT failure         |
| **“Could not recognize speech”** | Low-quality or silent audio; adjust `source_lang` or mic permissions |
| **Unicode errors on Windows**    | Run terminal in UTF-8 mode: `chcp 65001`                             |

---

## 📜 License

This repository is open-sourced for **educational and research purposes**.
Please review third-party licenses (gTTS, Edge TTS, yt-dlp, pytube, librosa, etc.) before any commercial use.

---

## 🙏 Acknowledgments

Built with ❤️ using:

* Python SpeechRecognition
* gTTS, Edge TTS
* librosa, moviepy
* yt-dlp, pytube
* Hugging Face Datasets (optional, Module 2)

---

Would you like me to make it **auto-formatted for GitHub (with emoji badges, install shields, and preview GIF placeholders)**?
That would make your repo look even more professional and ready for public view.
