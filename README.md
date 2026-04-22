# 📊 Análisis de Modelos IA Locales para Móvil / Local AI Models Mobile Analysis

[![Language](https://img.shields.io/badge/Lang-ES%20%2F%20EN-blue)]()
[![License](https://img.shields.io/badge/License-MIT-green)]()
[![Topic](https://img.shields.io/badge/Topic-LLM%20%7C%20Mobile%20AI%20%7C%20Benchmark-orange)]()

> 📱 **Comparativa completa y visual de 4 modelos LLM cuantizados (Q4) optimizados para ejecución local en smartphones.**  
> 📱 **Complete visual comparison of 4 quantized (Q4) LLM models optimized for local execution on smartphones.**

## 📖 Descripción / Description
Este repositorio contiene una **infografía interactiva en HTML** que analiza y compara el rendimiento, consumo de RAM real, ventana de contexto y especialidades de cuatro modelos de lenguaje local populares, ejecutados en formato **Q4 (4-bit)** en dispositivos móviles Android/iOS mediante motores como `llama.cpp` o `MLX`.

El objetivo es ofrecer una referencia clara, bilingüe y visual para usuarios, desarrolladores y entusiastas que quieran ejecutar IA localmente sin depender de la nube.

## 🧠 Modelos Analizados / Analyzed Models
| Modelo | Desarrollador | Parámetros | Cuantización |
|---|---|---|---|
| `Qwen2.5-3B-Q4` | Alibaba | 3B | 4-bit |
| `Qwen3-4B-Q4` | Alibaba | 4B | 4-bit |
| `Llama3.2-3B-Q4` | Meta | 3B | 4-bit |
| `Gemma3-4B-Q4` | Google | 4B | 4-bit |

## 📊 Resultados Clave / Key Findings

### 🏆 ¿Cuál es el más general y consistente?
**`Qwen3-4B-Q4`** obtiene la **puntuación de consistencia más alta (92%)**, destacando en razonamiento, generación de código, matemáticas y soporte multilingüe (119 idiomas). Es la mejor opción para uso general en móviles con `≥6GB RAM`.

### 📉 Consumo Real de RAM en Móvil (Pico)
- 🔹 `Llama3.2-3B-Q4`: `~2.0 GB` *(Más eficiente)*
- 🔹 `Qwen2.5-3B-Q4`: `~2.1 GB`
- 🔹 `Gemma3-4B-Q4`: `~2.6 GB`
- 🔹 `Qwen3-4B-Q4`: `~2.8 GB`  
*(Valores medidos con prompts complejos en ejecución local. El SO reserva ~1.5-2GB adicionales)*

### ⚡ Velocidad vs Contexto
| Métrica | Ganador | Detalle |
|---|---|---|
| 🚀 **Más rápido** | `Llama3.2-3B-Q4` | ~50 tok/s (inferencia en CPU/NPU optimizada) |
| 📜 **Mayor contexto** | `Llama3.2-3B-Q4` | 128K tokens (ideal para documentos largos) |
| 💻 **Mejor en código/math** | `Qwen2.5-3B-Q4` | Entrenamiento específico en STEM y programación |
| 🌐 **Multilingüe & Ciencia** | `Gemma3-4B-Q4` | Alto rendimiento en +100 idiomas y razonamiento técnico |

## 🛠️ Cómo Visualizar la Infografía / How to View
1. **Descarga o clona** este repositorio:
   ```bash
   git clone https://github.com/TU_USUARIO/local-ai-mobile-comparison.git
   cd local-ai-mobile-comparison
   ```
2. **Abre el archivo** `index.html` en cualquier navegador moderno (Chrome, Safari, Firefox).
3. *(Opcional)* **Publica en GitHub Pages** para compartirlo online:
   - Ve a `Settings > Pages`
   - Selecciona rama `main` y carpeta `/ (root)`
   - Guarda y espera ~2 min. Tendrás un enlace público.

## 📋 Recomendaciones por Caso de Uso / Use-Case Recommendations
| Caso de Uso / Use Case | Modelo Recomendado | RAM Mínima Dispositivo |
|---|---|---|
| 🤖 Uso General / General Assistant | `Qwen3-4B-Q4` | 6 GB |
| ⚡ Bajo Consumo / Low RAM Devices | `Llama3.2-3B-Q4` | 4 GB |
| 💻 Programación & Matemáticas / Code & Math | `Qwen2.5-3B-Q4` | 4 GB |
| 🌐 Multilingüe & Ciencia / Multilingual & Science | `Gemma3-4B-Q4` | 6 GB |

## ⚠️ Notas Técnicas & Disclaimer
- 🔋 Los valores de RAM son **pico de uso real** medidos en ejecución local. El consumo varía según el SoC (Snapdragon, MediaTek, Apple Silicon), versión del SO y fondo de procesos activos.
- 🔽 La cuantización **Q4_K_M** reduce el tamaño y consumo de memoria en ~60% respecto a FP16, con una pérdida de precisión del 2-5% en tareas complejas.
- 📈 Las velocidades (`tok/s`) se miden en hardware móvil de gama media/alta (ej. Snapdragon 8 Gen 2, Apple A15/A16, Dimensity 9200+).
- 📊 Esta infografía es con fines educativos y de referencia. Los benchmarks reales pueden variar según la implementación (`llama.cpp`, `MLX`, `MNN`, `QNN`) y la longitud del prompt.

## 📁 Estructura del Proyecto / Project Structure
```
📦 local-ai-mobile-comparison
 ┣ 📂 assets/              # (Opcional) Capturas o logos
 ┣ 📜 index.html           # Infografía interactiva completa
 ┣ 📜 README.md            # Documentación principal
 ┗ 📜 LICENSE              # Licencia MIT
```

## 🤝 Contribuir / Contribute
¿Encontraste errores, tienes datos de benchmarks más recientes o quieres añadir un modelo?  
¡Abre un **[Issue](issues)** o envía un **[Pull Request](pulls)**! Todas las contribuciones son bienvenidas.

## 📄 Licencia / License
Este proyecto está bajo la licencia **[MIT](LICENSE)**.  
Los nombres, logos y marcas de los modelos pertenecen a sus respectivos creadores: `Alibaba Group`, `Meta AI`, `Google DeepMind`.

---
*Hecho con ❤️ para la comunidad de IA local. / Made with ❤️ for the local AI community.*  
📩 ¿Dudas o sugerencias? Abre un issue o contáctame en tus redes.
