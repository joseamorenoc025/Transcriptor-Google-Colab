# 🎙️ Transcriptor Legislativo

> Herramienta para generar actas formales a partir de audio de sesiones legislativas, ejecutable en Google Colab.

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org)
[![Whisper](https://img.shields.io/badge/Modelo-OpenAI%20Whisper-green.svg)](https://github.com/openai/whisper)
[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)

## ✨ Características

- 🔊 **Transcripción precisa**: Usa Whisper (`large-v3` o `medium`) optimizado para español.
- 🧠 **Contexto legislativo**: Prompt inicial con términos como *quórum*, *orden del día*, *acta*.
- 👤 **Corrección inteligente de nombres**: Coincidencia difusa (`rapidfuzz`) para normalizar variaciones de nombres de legisladores.
- 📄 **Generación de Word formal**: Formato institucional con encabezado, metadatos, texto justificado y espacio para firmas.
- 🔀 **Diarización opcional**: Separación automática de interlocutores con Pyannote (con fallback elegante si falla).
- 🗂️ **Soporte para audios largos**: Manejo de VRAM y caché para sesiones de +30 minutos.
- ⬇️ **Descarga manual**: Flujo sencillo en Colab sin configuración de almacenamiento externo.

## 🚀 Uso rápido en Google Colab

1. Abre [Google Colab](https://colab.research.google.com/) y crea una nueva notebook.
2. Copia y pega el contenido completo de `transcriptor_legislativo.py` en una celda.
3. Ejecuta la celda (`Ctrl + Enter`).
4. Sube tu archivo de audio (`.mp3`, `.wav`, `.m4a`, etc.).
5. Si activaste diarización, pega tu [token de Hugging Face](https://huggingface.co/settings/tokens) cuando se solicite.
6. Espera a que finalice y descarga el archivo `_ACTA.docx` generado.

## ⚙️ Personalización

Edita estas variables al inicio del script según tu contexto:

```python
USAR_DIARIZACION = True  # False para transcripción continua sin separación de voces
NOMBRES_CANONICOS = ["Nombre Apellido", "Otro Legislador"]  # Lista de nombres oficiales

Términos y correcciones específicas
Para adaptar el prompt y las correcciones a tu entidad legislativa, modifica:
chuleta_ia: Incluye términos locales, nombres de cargos, geografía.
correcciones (dentro de corregir_nombres_fuzzy): Ajusta el umbral de similitud o añade reglas específicas.
📦 Dependencias principales
El script instala automáticamente:
openai-whisper: Transcripción de audio a texto.
python-docx: Generación de documentos Word.
rapidfuzz: Coincidencia difusa para nombres.
pyannote.audio: Diarización de hablantes (opcional).
ffmpeg: Decodificación de audio (requisito del sistema).
🤝 Contribuciones
¿Encontraste un error o tienes una mejora? ¡Las PRs son bienvenidas!
Haz fork del repositorio.
Crea una rama con tu cambio (git checkout -b feature/nueva-funcionalidad).
Commit y push (git commit -m "Añadir: descripción clara").
Abre un Pull Request describiendo el cambio.
📄 Licencia
Este proyecto está bajo la Licencia MIT. Ver el archivo LICENSE para más detalles.
