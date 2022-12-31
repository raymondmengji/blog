---
title: "Exam Writing I"
tags: [exams]
description: Thought process behind writing an exam question
author:
    name: Peyrin Kao
redirect_from: /exam-writing-i/
---

Here's the first of hopefully a longer series of posts about writing solid exam questions. I'll be focusing on CS 161-style questions in this guide, but the ideas should be applicable to other topics as well!

I've been stuck forever on making a structured how-to guide for exam writing, because I guess it's pretty open-ended and not something you can create a checklist for. So for now I'll start by writing out my thought processes behind some exam questions I wrote and hopefully that will uncover some tips along the way.

This post focuses on CS 161 Summer 2020 Midterm, Q4: steg. Here are links to [the question](https://cs161.org/assets/exams/mt1/su20mt.pdf#page=8) and [the solution](https://cs161.org/assets/exams/mt1/su20mtsolutions.pdf#page=12).


## Brainstorming question idea

I got the idea for this question from a common misconception I kept seeing on Piazza and office hours: students thought that because the stack grows down, the `gets` function must write data on the stack downwards as well. That got me to thinking how it'd be interesting to test understanding of memory safety vulnerabilities by having people write an exploit downwards on the stack.

In my opinion, coming up with this idea is the most open-ended and trickiest part of writing an exam question. Once you have the idea tied down, writing out the subparts comes more naturally. Also, as an exam editor, it's a lot easier to fix up subparts than to come up with another new idea from scratch.


## Scaffolding the question

I knew I wanted to make a buffer overflow exploit writing downwards, but didn't really know what that would look like, so I started out with the most simple buffer overflow (project 1 question 1):

```c
void display() {
  char buf[8];
  gets(buf);
}

int main() {
  display():
}
```

For reference, here's a 161-style stack diagram of this program:

```
|  RIP of main   |
|  SFP of main   |
| RIP of display |
| SFP of display |
|  char buf[8]   |
```

Problem: If writing downwards from `buf`, there's nothing to overflow! I played around with the code a bit and realized that I could put the buffer in `main`, above the RIP and SFP of `display`, which led to the code snippet in the question:

```c
void display(char *buf) {
  steg(buf);
}

int main() {
  char door[8];
  display(&door):
}
```

I called my new downwards-writing function `steg` because...`gets` backwards. Real clever.

At this point, I wrote out a working exploit before putting together any subparts, taking some mental notes on how I worked through this with no subpart guidance or multiple-choice answers to select from. This helps to get a sense of how difficult the question is, and how the subparts should be structured.


## Easy subparts

Q4.1-Q4.3: I like asking students to stack diagrams before starting any memory safety vulnerabilities. Stack diagrams are something students have seen in class many times before, so they serve as a nice gentle introduction to the question. Having this easy part ensures that they aren't immediately overwhelmed by difficulty and gives them some time to internalize the question while working through these parts.

I can't remember if there was a more profound reason I changed `door[8]` to `door[4]`, but I *think* it happened here, where I realized that it was easiest for each blank on the stack diagram to represent 4 bytes.

Q4.4: Next, I wanted to familiarize students with the `steg` function since it's the new, unusual part of this question. This subpart only requires basic understanding of buffer overflows to answer, and mainly exists to make sure that students understand how `steg` is writing downwards. It's a good reminder for students to re-read the question (especially the documentation for `steg`) in case they miss it.


## Medium subparts

With a better understanding of the `steg` function, it's time to actually exploit the program.

When writing this, I started out by writing the correct exploit myself, before converting it to multiple-choice questions.

Q4.5: I realized that writing downwards has a really obscure off-by-one trick. For example, if you write `steg(buf)` and `&buf = 0x10`, then your write actually starts at the LSB of the current word before going down to the next word. An alternative is to have `steg` start writing at `&buf-1`, but that also felt quite obscure; why would a `gets`-derived function not start writing at its pointer? This didn't seem like it was testing anything useful, so I made all the answer choices here 1 mod 4 to ensure that no one would get caught up with the off-by-one trick. My hope was that if you knew one word had to be overwritten, you would notice that 4 bytes isn't an answer choice and either default to the nearest (5) or correctly reason out where that extra byte came from. Having 4 as a possible answer would just be too tricky for no reason, I think.

Q4.6-Q4.7: Unlike the off-by-one, the need to reverse the address of shellcode is actually testing something important (little-endianness and the order of writing on the stack), so I did put the reversed answer as a possible choice. (We did give partial credit for people who chose that option.) As a way to remind people about the backwards writing, and to avoid double jeopardy for missing that idea, I only included `REV_SHELLCODE` and not `SHELLCODE`.


## Medium-hard subparts

This wasn't designed to be a really hard question, so I don't think it had any A-level subparts (parts that only an A student would get right). The last two parts are probably medium-hard parts that test deeper understanding of this question and touch on some other memory safety topics.

Q4.8: I wanted to include a bit about memory safety defenses here, so I asked about stack canaries. I briefly thought about adding a harder exploit subverting stack canaries with this question, but it wasn't necessary on this exam, which already had a harder memory safety question.

The choice of an 8-byte shellcode in the previous subpart was influenced by this subpart. I think it used to be something like 39 bytes long (what we use in the project), but 8 is short enough to force you to really think about whether the canary is overwritten here.

Q4.9: This extends the previous part a bit more, since the yes/no could be guessed. I actually messed up the off-by-one trick when I wrote this question, so my intended answer (4 bytes) actually ended up being wrong. I didn't want to penalize students for missing the off-by-one trick, so we ended up accepting two answers here.