---
toc: True
comments: False
layout: post
title: Python Quiz
description: A quick quiz about some basic python syntax
type: hacks
courses: {'compsci': {'week': 2}}
---

```python
def ask_question(question, correct_answer):
    user_answer = input(question + " ")
    if user_answer.lower() == correct_answer.lower():
        return True
    else:
        return False

score = 0

questions = [
    ("What command do you use to output a message?", "print"),
    ("What code do you use to store input?", "variable"),
    ("What code do you use to define a function?", "def")
]

for question, answer in questions:
    if ask_question(question, answer):
        print("Correct!")
        score += 1
    else:
        print("Incorrect!")

print("\nQuiz completed!")
print("Your score:", score, "out of", len(questions))

```

    Correct!
    Correct!
    Correct!
    
    Quiz completed!
    Your score: 3 out of 3

