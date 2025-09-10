
---

### ## 🎯 Objective

This document presents a structured plan to identify and evaluate open-source AI models for analyzing student competence in Python programming. The goal is to assess a model's ability to generate insightful prompts that foster deep learning rather than providing direct solutions.

---

### ## 🛠️ Setup Instructions

All project deliverables are contained within this `README.md` file. No software installation or environment setup is required.

---

### ## 📝 Research Plan

My evaluation follows a two-stage methodology: Model Identification and Practical Validation.

#### Stage 1: Model Identification & Criteria

This stage focuses on selecting the most promising open-source models.

* **Candidate Models:**
    * **Code Llama (Meta):** A foundational model trained specifically on code, making it a prime candidate.
    * **StarCoder (BigCode):** A strong competitor with a focus on permissible open-source licensing.
    * **Mixtral (Mistral AI):** A high-performing sparse mixture-of-experts model known for its reasoning capabilities.

* **Primary Evaluation Criteria:**
    * **Code Comprehension:** The ability to understand not just syntax, but the underlying logic, intent, and potential misconceptions in a student's code.
    * **Instruction Following:** The model's capacity to reliably adopt a "Socratic Tutor" persona and adhere to negative constraints (e.g., "do not give the answer").
    * **Pedagogical Value:** The quality of the generated prompts—whether they guide students to discover errors and deepen their conceptual understanding.
    * **Accessibility:** The feasibility of running the model locally or via an API for testing and potential deployment.

#### Stage 2: Practical Validation & Testing

This stage involves testing the selected model (initially **Code Llama 13B**) against a custom-built benchmark.

* **Process:**
    1.  **Create Test Suite:** Develop a curated set of ~20 beginner Python snippets, each containing a common conceptual error (e.g., mutable default arguments, variable scope issues, inefficient loops).
    2.  **Prompt Engineering:** Design a master prompt that instructs the model to act as a helpful tutor, analyze the code, and ask a single, guiding question to help the student identify their mistake.
    3.  **Qualitative Analysis:** Evaluate each generated question against a rubric to measure its effectiveness.

* **Evaluation Rubric for Prompts:**
    * **Relevance:** Does the question target the core conceptual flaw?
    * **Guidance:** Does it hint at the solution without revealing it?
    * **Clarity:** Is the question unambiguous for a novice programmer?
    * **Depth:** Does it encourage thinking about the "why," not just the "what"?

---

### ## 🤔 Reasoning

#### What makes a model suitable for high-level competence analysis?

A suitable model must possess capabilities beyond simple code correction. The key attributes are:

* **Conceptual Abstraction:** It must move beyond syntax to recognize underlying CS concepts (e.g., identifying algorithmic inefficiency, not just a slow loop).
* **Logical Inference:** It needs to infer the student's probable mental model to understand *why* they made a mistake, enabling it to address the root cause of the error.
* **Controllable Generation:** The model must be highly steerable, allowing it to generate open-ended, Socratic questions rather than declarative solutions.

#### How would you test whether a model generates meaningful prompts?

A prompt's value is tested through a structured, qualitative comparison:

1.  **Establish Baseline:** An expert Python instructor writes "gold standard" guiding questions for each code snippet in the test suite.
2.  **Generate & Compare:** The AI model is prompted to generate a question for the same snippet.
3.  **Evaluate via Rubric:** Both the AI and expert prompts are blindly scored against the rubric (Relevance, Guidance, Clarity, Depth). A "meaningful" AI prompt is one that scores comparably to the human expert's.

#### What trade-offs might exist between accuracy, interpretability, and cost?

These three factors are in constant tension when deploying AI systems:

* **Accuracy vs. Cost:** State-of-the-art accuracy requires larger models (e.g., 70B+ parameters), which are significantly more expensive to host and run than smaller, less capable models.
* **Accuracy vs. Interpretability:** The most accurate models (LLMs) are "black boxes," making it difficult to understand their reasoning. This is a risk in education, where an inexplicably flawed suggestion can be harmful. Simpler, interpretable models lack this high-level accuracy.
* **Interpretability vs. Cost:** Techniques to make LLMs more interpretable require additional computational overhead, further increasing operational costs.

The ideal solution must balance "good enough" accuracy with acceptable costs and manageable risks from low interpretability.

#### Why did you choose the model you evaluated, and what are its strengths or limitations?

My primary choice for evaluation is **Code Llama**.

**Reason for Choice:** Code Llama was chosen for its **code-native foundation**. Unlike generalist models, it was pre-trained on a massive 500B token corpus of code, giving it a superior intrinsic understanding of programming logic, patterns, and languages. It is open-source, well-documented, and available in multiple sizes.

* **Strengths:**
    * **Specialized Knowledge:** Deep, inherent understanding of code syntax, idioms, and structure.
    * **Proven Performance:** State-of-the-art results on major coding benchmarks.
    * **Instruction-Tuned:** Pre-trained variants exist that are optimized for following complex, task-oriented prompts.

* **Limitations:**
    * **Not a Teacher:** It is an expert programmer, not an expert educator. It lacks an innate understanding of pedagogy and must be carefully guided.
    * **Risk of Over-Correction:** May suggest professionally optimal but conceptually advanced solutions that could confuse a beginner.
    * **Potential for Hallucination:** Can generate plausible but incorrect advice, which is particularly dangerous in an educational context.

---

### ## 📚 References

* **Code Llama:** [https://ai.meta.com/blog/code-llama-large-language-model-coding/](https://ai.meta.com/blog/code-llama-large-language-model-coding/)
