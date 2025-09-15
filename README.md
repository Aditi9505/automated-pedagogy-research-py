Evaluating Open Source Models for Student Competence Analysis

This project explores and evaluates the use of open source AI models for assessing and enhancing student learning in Python. The goal is to move beyond simple code correctness and into the realm of conceptual understanding, identifying misconceptions, and fostering deeper learning.

📝 Research Plan: A Structured Approach
My research plan is divided into two phases to ensure a thorough and practical evaluation.

Phase 1: Model Identification & Criteria Setting
I will begin by identifying a shortlist of open source LLMs from platforms like Hugging Face. The primary criteria for selection will be:

Suitability for Code Analysis: Models explicitly trained on code (e.g., Code Llama, CodeBERT) are prioritized.

Open Source & Accessibility: The model must be freely available and have a clear license for academic use.

Computational Footprint: I will favor models that are relatively small and can be run on consumer-grade hardware for practical, in-classroom deployment.

Phase 2: Hands-on Evaluation
From the shortlist, I will perform a targeted evaluation using a custom Python script. This script will simulate the student-teacher interaction by feeding the model student-written code and then assessing the quality of the prompts it generates. This allows for a direct, qualitative assessment of the model's performance in our specific use case.

🧠 Reasoning and Critical Analysis
What makes a model suitable for high-level competence analysis?
A model is suitable for this task if it demonstrates semantic understanding and pedagogical reasoning. It must be able to:

Identify Underlying Logic: Go beyond syntax errors and understand the student's logical intent and problem-solving strategy.

Generate Socratic Prompts: Formulate questions that guide the student toward a solution without giving it away. For instance, instead of fixing a bug, the model should ask, "What happens if the input is an empty list?" to prompt critical thinking about edge cases.

Detect Misconceptions: Recognize patterns of incorrect reasoning (e.g., confusing == with =) and address the underlying concept rather than just the immediate error.

Maintain a Socratic Tone: The model's prompts must be encouraging and non-judgmental, fostering a safe learning environment.

How would you test whether a model generates meaningful prompts?
I would employ a qualitative, rubric-based evaluation combined with a human-in-the-loop approach.

Create Test Scenarios: I would prepare a set of Python code snippets containing common student errors, misconceptions, and inefficient solutions.

Rubric Development: A scoring rubric would be created based on criteria such as:

Relevance (1-5): Does the prompt address the core issue in the code?

Effectiveness (1-5): Does the prompt encourage the student to think critically instead of just applying a fix?

Clarity (1-5): Is the prompt easy for a student to understand?

Expert Validation: The model's generated prompts would be scored against this rubric by a Python expert. This process would provide both quantitative and qualitative data to determine the model's suitability and highlight its limitations.

Trade-offs: Accuracy, Interpretability, and Cost
The ideal model balances these three factors. A massive, highly accurate LLM might give excellent prompts but be too slow or expensive for real-time educational feedback. A smaller model, while less accurate, could be deployed locally at a low cost, providing instant feedback. The most crucial trade-off is between accuracy and interpretability. While a model may be "accurate" in generating a correct prompt, if its logic is a "black box," it's hard for an instructor to trust it. For an educational tool, some level of interpretability (e.g., an explanation of why the prompt was generated) is a valuable feature.

Model Choice: Initial Evaluation with Code Llama
For this task, I would choose to evaluate Code Llama due to its specific focus on code.

Strengths: Its core strength is its understanding of code structure and semantics, making it uniquely suited for analyzing Python code. Being an open-source model developed by Meta, it provides a powerful, free foundation that can be fine-tuned.

Limitations: Its primary limitation is its size and computational requirements. Deploying a larger variant for real-time analysis would likely require cloud infrastructure. Moreover, like many LLMs, it can "hallucinate," potentially providing incorrect or misleading feedback. A robust fine-tuning and validation process would be necessary to mitigate these risks and tailor its responses to be truly effective in an educational context.

🛠️ Reproducibility and Setup Instructions
To run my evaluation script and reproduce this research, follow these steps:

Clone this repository:

git clone [[your_repo_link](https://github.com/Aditi9505/automated-pedagogy-research-py)]
cd [automated-pedagogy-research-py]

Install dependencies: pip install -r requirements.txt

Run the evaluation script: python evaluate_model.py
