# The Mood Machine

The Mood Machine is a simple text classifier that begins with a rule based approach and can optionally be extended with a small machine learning model. It tries to guess whether a short piece of text sounds **positive**, **negative**, **neutral**, or even **mixed** based on patterns in your data.

This lab gives you hands on experience with how basic systems work, where they break, and how different modeling choices affect fairness and accuracy. You will edit code, add data, run experiments, and write a short model card reflection.

---

## Repo Structure

```plaintext
├── dataset.py         # Starter word lists and example posts (you will expand these)
├── mood_analyzer.py   # Rule based classifier with TODOs to improve
├── main.py            # Runs the rule based model and interactive demo
├── ml_experiments.py  # (New) A tiny ML classifier using scikit-learn
├── model_card.md      # Template to fill out after experimenting
└── requirements.txt   # Dependencies for optional ML exploration
```

---

## Getting Started

1. Open this folder in VS Code.
2. Make sure your Python environment is active.
3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Run the rule-based starter:

    ```bash
    python main.py
    ```

If pieces of the analyzer are not implemented yet, you will see helpful errors that guide you to the TODOs.

To try the ML model later, run:

```bash
python ml_experiments.py
```

---

## What You Will Do

During this lab you will:

- Implement the missing parts of the rule based `MoodAnalyzer`.
- Add new positive and negative words.
- Expand the dataset with more posts, including slang, emojis, sarcasm, or mixed emotions.
- Observe unusual or incorrect predictions and think about why they happen.
- Train a tiny machine learning model and compare its behavior to your rule based system.
- Complete the model card with your findings about data, behavior, limitations, and improvements.
- The goal is to help you reason about how models behave, how data shapes them, and why even small design choices matter.

---

## Tips

- Start with preprocessing before updating scoring rules.
- When debugging, print tokens, scores, or intermediate choices.
- Ask an AI assistant to help create edge case posts or unusual wording.
- Try examples that mislead or confuse your model. Failure cases teach you the most.

## Task Summary

The main idea of this activity was showing students how even a small sentiment analyzer depends a lot on the rules and data it is built from. Students had to understand the difference between a rule-based model, which follows exact keyword logic, and a small ML model, which learns patterns from labeled examples. I think students would probably struggle most with labeling posts that feel ambiguous, mixed, sarcastic, or full of slang and emojis, because those are the cases where simple systems start breaking down. AI was helpful for brainstorming more realistic sample posts, explaining the code structure, and suggesting small improvements to the scoring logic, but it could also be misleading when it sounded too confident about why a prediction failed or suggested fixes that were bigger than the actual issue. Because of that, students really need to check AI suggestions against the dataset, the labels, and the actual outputs from the model. One way I would guide a student without giving away the answer is by asking which exact word or rule changed the score and whether that matches the label they expected. That usually helps them figure out whether the issue is coming from the vocabulary, the labels, or the scoring logic itself.
