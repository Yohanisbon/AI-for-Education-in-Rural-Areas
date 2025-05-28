## 🌍 AI Code Sample – Translating Kiswahili to English for Students

This example demonstrates how to use an AI model to translate learning content or questions between Kiswahili and English — helping students in rural Tanzania understand their studies better.

---

### 🧠 Why Translation Matters

- Many rural students speak Kiswahili but must learn subjects written in English.
- Translation enables them to understand science, math, and exam instructions more clearly.
- This AI-powered model helps bridge that educational gap.

---

### ⚙️ Python Code

```python
# Install the transformers library if not installed:
# pip install transformers

from transformers import pipeline

# Load the translation pipeline
translator = pipeline("translation", model="Helsinki-NLP/opus-mt-sw-en")

# Example Kiswahili sentence from a science textbook
kiswahili_text = "Jua hutoa mwanga na joto muhimu kwa maisha duniani."

# Translate to English
result = translator(kiswahili_text)

# Print the result
print("Kiswahili:", kiswahili_text)
print("English Translation:", result[0]['translation_text'])
