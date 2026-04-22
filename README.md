# 📱 AI Models Local Infographic & RAM Simulator

> **Interactive web dashboard comparing Qwen2.5-3B, Qwen3-4B, Llama3.2-3B & Gemma3-4B for mobile/edge deployment.**  
> Analyze real-world RAM consumption, context limits, benchmark scores, and device compatibility in a bilingual, fully responsive interface.

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white)](https://www.chartjs.org)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

---

## 🌐 Live Demo
🚀 **[View Live Demo](https://yourusername.github.io/your-repo-name)** *(Replace with your GitHub Pages / Netlify / Vercel URL)*

📸 *Add screenshots or a GIF demo here:*
```
📱 RAM Simulator          📊 Interactive Charts         🔄 Model Comparator
┌───────────────────────┐  ┌───────────────────────┐  ┌───────────────────────┐
│  [6GB] [8GB] [12GB]   │  │  ▓▓▓▓▓▓▓▓▓▓  Qwen3    │  │  Model A    VS Model B │
│  🤖 Android / 🍎 iOS  │  │  ▓▓▓▓▓▓▓▓▓   Llama    │  │  RAM: 1.8GB | 2.5GB   │
│  ✅ Qwen2.5-3B Fits   │  │  🕸️ Radar Skills      │  │  MMLU: 54   | 62      │
└───────────────────────┘  └───────────────────────┘  └───────────────────────┘
```

---

## ✨ Key Features
| Feature | Description |
|---------|-------------|
| 📊 **4 Interactive Charts** | RAM usage, context window, specialty radar, and benchmark comparison (MMLU, GSM8K, HumanEval) |
| 📱 **Realistic RAM Simulator** | Predicts model feasibility on 6GB/8GB/12GB devices accounting for **Android 14** or **iOS 17/18** overhead + safety buffer |
| 🔄 **Side-by-Side Comparator** | Select any 2 models to highlight differences in specs, scores, and use-cases |
| 🌐 **Bilingual (ES/EN)** | One-click toggle with full translation of UI, charts, and documentation |
| 🎯 **Best-Use Recommendations** | Curated suggestions for Edge/Mobile, Coding, Math/Science, and Vision/Multimodal workloads |
| 📋 **Complete Specs Table** | Architecture, GGUF size, context limits, licenses, and estimated inference speeds |
| ⚡ **Zero Build Step** | Single `index.html` file. CDN-hosted libraries. Open directly in any browser. |
| 📱 **Fully Responsive** | Mobile-first design with smooth animations and modern glassmorphism UI |

---

## ⚙️ How the RAM Simulator Works
The simulator doesn't just show file size. It calculates **real usable RAM** after accounting for OS background processes and safety margins to prevent OOM (Out of Memory) crashes.

### 🔢 Formula
```
Available RAM = Total Device RAM - OS Base Usage - Safety Buffer
```

| OS | Base Usage | Safety Buffer | Total Reserved | Source |
|----|------------|---------------|----------------|--------|
| 🤖 **Android 14** | ~2.5 GB | 0.5 GB | **3.0 GB** | `system_server`, ZRAM, SurfaceFlinger, background services |
| 🍎 **iOS 17/18** | ~1.8 GB | 0.4 GB | **2.2 GB** | `kernel`, SpringBoard, system caches, memory compression |

### 📏 Model Memory Estimation
- **Base Size:** `Q4_K_M` GGUF quantization (actual file size on disk)
- **KV Cache Overhead:** ~1.5 MB per 4K tokens during inference
- **Status Indicators:**
  - ✅ **Comfortable:** >0.5 GB free for context & system stability
  - ⚠️ **Tight:** <0.5 GB free. May throttle or limit context
  - ❌ **No Fit:** Model exceeds available RAM. Will crash or OOM

---

## 🛠️ Tech Stack
| Layer | Technology |
|-------|------------|
| **Structure** | HTML5 (Semantic) |
| **Styling** | Tailwind CSS (via CDN) + Custom CSS Variables |
| **Charts** | Chart.js 4.x + `chartjs-plugin-datalabels` |
| **Logic** | Vanilla JavaScript (ES6+) |
| **Typography** | Inter (Fontsource) |
| **Animations** | CSS `@keyframes` + Intersection Observer API |
| **Deployment** | GitHub Pages / Netlify / Vercel / Local File |

---

## 🚀 Quick Start & Deployment

### 🔹 Local Usage
1. Clone or download the repository:
   ```bash
   git clone https://github.com/yourusername/ai-models-infographic.git
   cd ai-models-infographic
   ```
2. Open `index.html` in your browser. **No server required.**

### 🔹 Deploy to GitHub Pages
1. Push to a GitHub repository.
2. Go to `Settings → Pages → Source: main branch → /root`.
3. Your dashboard will be live at `https://yourusername.github.io/ai-models-infographic`

### 🔹 One-Click Deploy
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/yourusername/ai-models-infographic)
[![Deploy to Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/yourusername/ai-models-infographic)

---

## 📐 Project Structure
```
ai-models-infographic/
├── index.html          # Single-file application (HTML + CSS + JS)
├── README.md           # Documentation (this file)
├── LICENSE             # MIT License
└── assets/             # (Optional) Screenshots, icons, or branding
```
*All logic, styling, and translations are embedded in `index.html` for maximum portability.*

---

## 📚 Data Sources & Methodology
| Metric | Source / Estimation |
|--------|---------------------|
| **GGUF Q4 Size** | `llama.cpp` conversion output (`llama-quantize` Q4_K_M) |
| **RAM Usage** |实测 memory allocation on Snapdragon 8 Gen 2 / Apple A16 + `llama.cpp` overhead |
| **Benchmarks** | Community aggregated scores (MMLU, GSM8K, HumanEval) from official model cards & HuggingFace |
| **Inference Speed** | `llama.cpp` on 4 threads (CPU) + Metal/NNAPI acceleration where applicable |
| **Context Limit** | Official architecture specs (RoPE scaling, KV cache limits) |
| **OS Overhead** | Android Developers docs, Apple Memory Management guidelines, real-device profiling |

> ⚠️ **Disclaimer:** Values are **approximations** based on public documentation, community testing, and typical mobile workloads. Actual performance varies by device SoC, thermals, background apps, and `llama.cpp` build flags.

---

## 🤝 Contributing
Contributions are welcome! Here's how to help:
1. 🍴 Fork the repository
2. 🌿 Create a feature branch: `git checkout -b feat/add-gemma-2b`
3. 💻 Make your changes (keep it single-file if possible)
4. 📝 Commit with conventional messages: `feat: add memory profiling for iOS 18`
5. 🚀 Push and open a Pull Request

### 🔍 Looking for:
- Updated benchmark data from 2025 H1 releases
- Additional OS profiles (HarmonyOS, Ubuntu Touch)
- New model comparisons (Phi-3-mini, Mistral-7B-Q4, etc.)
- Accessibility improvements (WCAG 2.1 AA)
- Performance optimizations for low-end devices

---

## 📄 License
This project is licensed under the **MIT License** – see the [`LICENSE`](LICENSE) file for details.  
You are free to use, modify, and distribute this infographic for personal, educational, or commercial purposes.

---

## 🙏 Acknowledgments
- **Chart.js Team** for the robust visualization library
- **TailwindCSS** for utility-first styling
- **llama.cpp Community** for quantization tools & real-world testing data
- **Model Developers**: Meta AI, Alibaba Qwen Team, Google DeepMind
- **Open Source Contributors** who benchmark and share GGUF performance metrics

---

## 📬 Contact & Support
- 💬 Open an [Issue](https://github.com/yourusername/ai-models-infographic/issues) for bugs or data corrections
- 📧 Questions? Reach out via GitHub Discussions
- ⭐ **Found it useful?** Consider starring the repository!

---
*Made with ❤️ for the local AI & edge computing community.*  
*Last updated: `$(date +%B\ %Y)` | Framework: Vanilla JS + Tailwind + Chart.js*

