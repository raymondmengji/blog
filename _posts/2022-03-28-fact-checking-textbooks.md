---
title: Thoughts on Fact Checking Textbooks
tags: [content]
description: Thoughts on ways to vet course resources written in-house
author:
  name: Peyrin Kao
  url: https://peyrin.github.io
---

[CS 161's course textbook](https://textbook.cs161.org) was written entirely by instructors and TAs. Other classes in EECS also have notes and resources created in-house. Although this gives courses more freedom to align resources with the rest of the course, it's possible to make mistakes that could potentially go unchecked or confuse students.

Now that CS 161's course textbook is mostly complete, and our main priority isn't writing up missing sections, we can turn our attention to fact-checking the content in the textbook. This post compiles some preliminary thoughts we had when discussing how a rigorous fact-checking process would work.

## Who's Fact-Checking?

- It might be hard for TAs to fact-check resources when many of them learned from those resources as students.
- Can people who wrote the textbook fact-check it? Checking your own work might not catch misconceptions about the content that you have, or wordings that only make sense to you but not to everyone else. A counterpoint here is that re-reading your own work months after initially writing it still gives you a different perspective on it and can help catch errors.
- Can professors and other faculty members help fact-check? At the end of the day, any person fact-checking is still relying on human memory, which could be faulty or outdated. Also, when reading such a long set of resources, it can be easy to miss smaller mistakes, no matter how well-versed in the material you are.


## Citations

A possibly ambitious way to rigorously verify everything is to add inline citations from primary sources, including:
- Primary sources: RFCs and research papers
- Other textbooks: CS 161 used outside textbooks that we could reference.
- Other offical sources: Our [DNS chapter](https://textbook.cs161.org/network/dnssec.html#335-key-signing-keys-and-zone-signing-keys) cites a diagram from Cloudflare's website.

Personally, I like the way Wikipedia adds citations, as it's non-intrusive and easy to view any citation for verification. The citations don't need to be too formal; just some indication that someone besides course staff who is somewhat authoritative can validate what we're teaching students.

Also, listing sources has the nice side effect of giving students links to other resources if they want to learn more or see the material presented in a different way. 

It's too late for the CS 161 textbook, but for future similar projects, I would recommend tracking any resources consulted for the textbook, so that references can be added later, and any incorrect information can be traced back to its source.


## Opinionated Content

It's natural for some personal opinions to make their way into course content, but I think it's also important to be aware of when content becomes opinionated. Fact-checking material seems like a good way to identify when we subconsciously inject some opinions into content that might not be universally agreed upon by the broader academic community.

As an example, here's a statement from the [Mitigating Memory Safety Vulnerabilities](https://textbook.cs161.org/memory-safety/mitigations.html) chapter of the CS 161 textbook:

> However, because of legacy code and perceived performance concerns, memory-unsafe languages such as C are still prevalent today.
> 
> The one real performance advantage C has over a garbage collected language like Go is a far more deterministic behavior for memory allocation. But with languages like Rust, which are safe but not garbage collected, this is no longer an advantage for C.

Without looking further into this, I can't say conclusively where the debate about C stands today. Has its performance benefits been obsoleted by other memory-safe languages like Rust, to the point where legacy is the only reason why it's still used? Are the performance concerns that we claim are "perceived" actually legitimate?

CS 161 has taken the stance that there's no reason to start new projects in C and that legacy is the only thing keeping C around. This might have also created a cyclical problem where new TAs and instructors who went through the class end up teaching the same idea to future students. Maybe our stance is something that the academic community agrees on, or maybe it's a relatively unique opinion; it's hard to say one way or another without some sort of fact-checking process.

Another more subtle example of opinionated content appears in the [HMAC section](https://textbook.cs161.org/crypto/macs.html#85-hmac), which says:

> One of the best MAC constructions available is the HMAC, or Hash Message Authentication Code, which uses the cryptographic properties of a cryptographic hash function to construct a secure MAC algorithm.

CS 161 has taken the stance that HMAC is one of the best, if not the best HMAC construction. Is this something universally agreed upon by the security community? Again, we'd have to do some further fact-checking to find out.