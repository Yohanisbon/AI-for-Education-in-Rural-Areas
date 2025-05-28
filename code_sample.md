# 💻 AI Code Sample – AI-Powered Question Answering for Rural Education

This Python script demonstrates how an AI assistant can answer students’ questions
based on local science curriculum. It's designed for mobile or offline-first learning
tools in under-resourced areas like rural Tanzania.

It uses Hugging Face's `transformers` library and a pre-trained question-answering model.
In a real deployment, the model could be optimized and translated into Kiswahili.

## 🧠 Objective
To simulate how an AI assistant can:
- Read local curriculum content
- Accept questions from students
- Give accurate, helpful answers in seconds
- Work even on low-end devices (with light models)

## ⚙️ Python Code

```python
# Install required library (uncomment if running for the first time)
# !pip install transformers

from transformers import pipeline

def main():
    # Load a Question-Answering pipeline
    try:
        qa_pipeline = pipeline("question-answering")
    except Exception as e:
        print(f"Error loading pipeline: {e}")
        return

    # Example learning content (could be from a textbook)
    context = (
        "The sun is a star at the center of the Solar System. "
        "It rises in the east and sets in the west. "
        "It gives off energy in the form of light and heat. "
        "This energy supports life on Earth and drives the climate."
    )

    # Example question from a student
    question = "What does the sun provide to the Earth?"

    # Feed the question and context into the model
    try:
        result = qa_pipeline(question=question, context=context)
        answer = result["answer"]
    except Exception as e:
        print(f"Error during question answering: {e}")
        return

    # Display the answer
    print("Question:", question)
    print("Answer:", answer)

if __name__ == "__main__":
    main()
