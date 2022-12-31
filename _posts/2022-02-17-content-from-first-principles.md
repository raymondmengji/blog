---
title: Content from First Principles
tags: [content]
description: Avoiding assuming prior knowledge when building course material
author:
    name: Peyrin Kao
redirect_from: /content-from-first-principles/
---

I presented CS 161's [Introduction to Cryptography](https://docs.google.com/presentation/d/1hVdnNDI7Pq_5tvTwM6uCzQ80lVtnpCEwWQZwS9Xl1jc) lecture as part of a teaching demo today, and there was a conversation about how this particular lecture and its corresponding [textbook chapter](https://textbook.cs161.org/crypto/intro.html) was explicitly designed to be an introduction that doesn't assume prior knowledge.

This idea is generalizable to any sort of content creation, but for our classes, it's most relevant in lecture slides and textbooks/notes, which is often the first exposure that students have to some new material.

- **Review prerequisites as they appear**: On slide 8, we explicitly mention the prerequisite for this unit (CS 70, discrete math and probability theory), while reassuring students that we'll review any prerequisite material when they come up. This helps reassure people who did poorly in CS 70 or haven't taken CS 70 that they aren't automatically at a disadvantage for this unit. Fortunately we don't need too much from that class so we have the luxury of reviewing material as it appears. In cases where that's not possible, links to review guides or relevant lectures from the prerequisite class might be nice.
- **Explicit definitions**: The entire first section of our cryptography unit is dedicated to explicitly defining terms. We also use bold text for any term that might not be immediately obvious to students to draw attention to them. ([See this post on using bolds and italics in slides.](/bolds-italics-underlines))
- **Make any assumptions explicit**: Especially with expert bias, it can be easy to have some fact or assumption internalized that students might not immediately recognize. For us, this was the fact that cryptographers always use Alice, Bob, Eve, and Mallory as stand-in characters. If you're just seeing cryptography for the first time, the roles of these characters is not immediately obvious, so we added an extra slide to explicitly define their roles.
- **Define non-ubiquitous real-world references**: Our slides frequently reference the NSA, but we started to realize that students (e.g. international students) might not necessarily know what the NSA is, so now there's a slide in the very first lecture clarifying what it stands for, who they are, and what their role is in our class. The line for what's ubiquitous is kind of gray--I thought that Apple's M1-based ARM system wouldn't be known by everyone unless you were fairly up-to-date with computing news, but some other TAs disagreed. I think we ended up leaving a footnote in the slide notes defining ARM and M1. When in doubt, it helps to talk it through!
- **Even if terms seem ubiquitous, redefine them in a technical context**: Many Internet-literate students probably already know what encryption and decryption are before our class, but this is certainly not true for all students. Also, these terms are so common even outside of computer science that people may have misconceptions about what they mean. On slide 18, we redefine these terms in a technical context to show how they'll be used in the context of our class (and the field of cryptography in general).

All of these points circle back to the same theme, which is to always be sure to define things when they aren't immediately obvious for students. This is true for technical terms, mathematical symbols (I find papers that don't explicitly define variables are exceedingly hard to read), acronyms, and even real-world references. Doing this **puts all students on equal footing** and creates a fairer learning environment where no one is at a disadvantage because of their pre-existing knowledge. It also makes course material more self-contained, which I think creates a smoother learning experience that doesn't require constantly searching outside resources for definitions.

More on notes/textbook writing in future posts!