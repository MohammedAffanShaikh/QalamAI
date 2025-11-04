
````markdown
# 🎙️ QalamAI Speech Translator  
> 🌍 Real-time & Batch AI Speech Translation Suite (Modules 1–4)

[![Python](https://img.shields.io/badge/Python-3.11%2B-blue?logo=python)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-Web%20App-black?logo=flask)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Build-Stable-brightgreen)]()
[![GitHub Repo](https://img.shields.io/badge/View_on-GitHub-black?logo=github)](https://github.com/MohammedAffanShaikh/QalamAI)

---

### 🧩 Overview

**QalamAI** is a modular AI-powered speech translator supporting:
- 🎤 **Speech-to-Text (STT)**
- 🌐 **Translation across 12 languages**
- 🔊 **Text-to-Speech (TTS)**
- ▶️ **Realtime OTT/YouTube & microphone translation**
- 💻 **Beautiful Flask web UI**

Built for **learners, researchers, and developers** exploring multilingual speech systems.

---

## 🏗️ Repository Structure

| Module | Folder | Description |
|:-------|:--------|:------------|
| **1️⃣ Module 1** | `speech-translator/module1/` | Environment setup & sanity checks |
| **2️⃣ Module 2** | `speech-translator/module2/` | Offline / batch translation toolkit |
| **3️⃣ Module 3** | `speech-translator/module3/` | OTT-style realtime translation (CLI) |
| **4️⃣ Module 4** | `speech-translator/module4/` | Flask web app (mic 🎙️, upload 📁, YouTube ▶️) |

---

## ✨ Features

✅ Speech-to-Text → Translate → Text-to-Speech  
✅ YouTube / OTT / Microphone support  
✅ Auto language detection  
✅ Human-like voices (EdgeTTS gendered when available)  
✅ Multi-pipeline audio handling (moviepy, ffmpeg, librosa, pydub)  
✅ Web UI + API endpoints  
✅ Modular architecture for flexibility

---

## 🌍 Supported Languages

| Code | Language | Code | Language |
|------|-----------|------|-----------|
| `en` | English | `hi` | Hindi |
| `pa` | Punjabi | `mr` | Marathi |
| `kn` | Kannada | `te` | Telugu |
| `ta` | Tamil | `gu` | Gujarati |
| `ml` | Malayalam | `bn` | Bengali |
| `or` | Odia | `ur` | Urdu |

---

## 🧰 Prerequisites

- **Python:** 3.11 – 3.13  
- **FFmpeg:** Required for audio processing  
  - ✅ Auto-handled in Module 4  
  - 🪄 Manual install (Windows): [Download FFmpeg](https://ffmpeg.org/download.html)  
  - Add `/bin` to your PATH  
- **YouTube Support:** via `pytube` or `yt-dlp`

---

## ⚡ Quick Start (Flask Web App – Module 4)

```bash
cd speech-translator/module4
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python app.py
````

🖥️ Open your browser at
👉 [http://127.0.0.1:5000](http://127.0.0.1:5000)

---

## 💻 Web App Pages

| Feature                     | Description                                      |
| --------------------------- | ------------------------------------------------ |
| 🎤 **Live Mic Translation** | Record → STT → Translate → TTS                   |
| 📁 **Upload Audio/Video**   | Supports mp3/mp4/wav with playback               |
| ▶️ **YouTube Translation**  | Downloads audio, chunks it, translates each part |
| 🗣️ **TTS Voices**          | EdgeTTS for male/female voices, fallback to gTTS |

---

## 🧪 Module 2 — Batch Translation Toolkit

Example commands:

```bash
# Convert MP3 to WAV
python convert_mp3_to_wav.py

# Run batch translation
python module2_batch_translator.py

# Fetch datasets from Hugging Face
python fetch_audio_datasets.py
```

📂 Outputs are saved under `outputs/` and logs under `logs/`.

---

## 🎬 Module 3 — OTT / Realtime (CLI Mode)

```bash
python module3_ott_realtime.py
```

Simulates realtime translation from **microphone** or **stream** input.
Perfect for testing live scenarios before UI integration.

---

## 🧠 Configuration Tips

| Setting          | Description                                         |
| ---------------- | --------------------------------------------------- |
| `source_lang`    | Optional hint to improve STT accuracy               |
| Audio Conversion | Auto pipeline: `moviepy → ffmpeg → librosa → pydub` |
| YouTube Download | Falls back to `yt-dlp` if `pytube` fails            |

---

## 🚑 Troubleshooting

| Problem                          | Fix                                         |
| -------------------------------- | ------------------------------------------- |
| **FFmpeg not found**             | Install FFmpeg and verify `ffmpeg -version` |
| **400/500 Bad Request**          | Check Flask console logs for details        |
| **“Could not recognize speech”** | Use clear audio, check mic permissions      |
| **Unicode errors (Windows)**     | Run terminal with UTF-8: `chcp 65001`       |

---

## 🌐 Deployment Options

* **Local (recommended for dev):** Flask + localhost
* **Render:** Deploy backend directly (Python buildpacks supported)
* **Netlify (frontend only):**
  Update `window.BACKEND_BASE_URL` in `index.html` → your Render URL

---

## 📸 Demo (Add your screenshots or videos!)

| Mic Translation                | YouTube Translation                    |
| ------------------------------ | -------------------------------------- |
| ![Mic Demo](docs/mic_demo.gif) | ![YouTube Demo](docs/youtube_demo.gif) |

---

## 📜 License

Licensed under the **MIT License**
See [LICENSE](LICENSE) for full details.

---

## ❤️ Acknowledgments

* 🧠 **SpeechRecognition** & **gTTS / EdgeTTS**
* 🎬 **MoviePy**, **librosa**, **pydub**
* 🌐 **yt-dlp**, **pytube**
* 🤗 **Hugging Face Datasets**

---

## ⭐ Contribute / Connect

Want to contribute or improve QalamAI?

```bash
git clone https://github.com/MohammedAffanShaikh/QalamAI.git
```

Pull requests are welcome!
💬 Contact: [@MohammedAffanShaikh](https://github.com/MohammedAffanShaikh)

---

> **Made with ❤️ by Mohammed Affan Shaikh**
> 🎧 Bridging voices across languages with AI.

```

---

### ✅ Optional Enhancements
You can also:
- Add a **project logo** (`/static/logo.png`) and link it at the top.  
- Record a short demo (screen recording of YouTube + mic translation).  
- Add shields for “Stars”, “Forks”, and “Issues” once public.

Would you like me to generate a **beautiful banner image** (like “QalamAI Speech Translator” with mic + waveform visuals) for the top of your README? It’ll make your GitHub page look premium.
```
