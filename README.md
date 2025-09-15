 Evaluating Open Source Models for Student Competence Analysis

A Research Plan for Prompting High-Level Student Competence
This document outlines a strategic research plan to evaluate and adapt open source AI models for a critical educational challenge: generating insightful prompts that assess a student's depth of understanding, rather than just their ability to produce correct code. My work uses Python learning as a case study to demonstrate this approach.

📝 Research Methodology
My evaluation strategy is a two-phased process designed to be both comprehensive and practical.

Phase 1: Identification and Selection of Candidate Models

I will begin with a targeted search on platforms like Hugging Face and GitHub for models specialized in code-related tasks. The key criteria for a promising candidate model will be:

Code-Centric Foundation: Prioritizing models pre-trained on large code corpora, such as Code Llama or CodeBERT. This ensures a robust understanding of code semantics and structure from the outset.

Open-Source and Accessible: The model must be freely available for research and educational purposes to ensure it aligns with the FOSSEE mission.

Scalability: A practical model must be adaptable. I will consider models that can be run on consumer-grade hardware for localized deployment or scaled on cloud infrastructure for broader use.

Phase 2: Targeted Hands-on Evaluation

I will select a model from my shortlist to perform a qualitative, hands-on evaluation using a Python script. This script will simulate the model's application by:

Feeding it student-written Python code snippets (e.g., incorrect syntax, inefficient logic, or conceptual errors).

Generating a diverse set of prompts or feedback from the model.

Manually assessing the quality, relevance, and pedagogical value of the output against a predefined rubric.

This phase will move beyond theoretical discussions to provide concrete evidence of the model's capabilities and limitations.

🧠 Critical Analysis and Rationale
1. What makes a model suitable for high-level competence analysis?
A model is suitable when it possesses strong semantic understanding and a capacity for pedagogical reasoning. It must be able to:

Discern Intent: Go beyond literal code to understand the student's problem-solving strategy. A good model identifies a flawed algorithm, not just a syntax error.

Generate Socratic Prompts: Instead of providing a direct fix, it should formulate guiding questions that prompt the student toward self-discovery. For instance, a meaningful prompt might ask, "What happens if you try to sort a list of mixed data types?" rather than, "Your code fails because of a type error."

Identify Misconceptions: It should be able to recognize and challenge a student's fundamental misunderstanding of a concept (e.g., mutable vs. immutable objects) and not just correct an isolated mistake.

2. How would you test whether a model generates meaningful prompts?
I would test the model's output using a human-in-the-loop validation process.

Rubric-Based Scoring: A qualitative rubric will score the model's prompts on three key criteria:

Relevance: Does the prompt directly address the conceptual issue in the code?

Clarity: Is the language of the prompt simple and encouraging for a learner?

Depth: Does the prompt guide the student to a deeper understanding, or does it just offer a hint for the immediate solution?

Comparative Analysis: The model's prompts will be directly compared against prompts written by an experienced human instructor for the same code. This comparison will provide a clear benchmark for the model's effectiveness and highlight areas where its "reasoning" falls short.

3. What trade-offs might exist between accuracy, interpretability, and cost?
The primary trade-off lies in choosing between a massive, highly accurate black-box model and a smaller, more interpretable one.

Accuracy vs. Cost: A larger model like Code Llama 70B may offer superior reasoning but is expensive and slow to run. A smaller, fine-tuned model (e.g., Code Llama 7B) may be less accurate but is more feasible for real-time, low-cost deployment in a classroom setting.

Accuracy vs. Interpretability: The "black-box" nature of large LLMs makes it difficult to understand why a specific prompt was generated. While such a model might be highly effective, its lack of interpretability could make it difficult for instructors to trust and integrate into their teaching. The optimal solution is one that provides a high degree of accuracy with a sufficient level of transparency.

4. Why did you choose Code Llama, and what are its strengths and limitations?
I chose Code Llama for initial evaluation because it is a powerful, open-source model specifically designed and trained for coding tasks.

Strengths: Its extensive training on a large code corpus provides a strong foundation for analyzing student Python. Its open-source nature means it can be fine-tuned to fit the precise pedagogical needs of a specific curriculum without licensing costs, offering both power and flexibility.

Limitations: Its size presents a significant computational challenge for local deployment, necessitating cloud infrastructure or a strategic use of smaller variants. Additionally, like all LLMs, Code Llama is susceptible to "hallucinations," which could lead to incorrect or misleading feedback for students. A rigorous, iterative validation process would be required to fine-tune the model's tone and ensure the accuracy of its prompts.

🛠️ Reproducibility and Setup Instructions
To run my evaluation script and reproduce this research, follow these steps:

Clone this repository:
git clone [[your_repo_link](https://github.com/Aditi9505/automated-pedagogy-research-py)]
cd [automated-pedagogy-research-py]

Install dependencies: pip install -r requirements.txt

Run the evaluation script: python evaluate_model.py
