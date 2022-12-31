---
title: "Making Reference Sheets I"
tags: [content]
description: Why we made our own reference card
author:
    name: Peyrin Kao
redirect_from: /making-reference-sheets-i/
---

CS 61C has used the [RISC-V reference card ("green card")](https://inst.eecs.berkeley.edu/%7Ecs61c/resources/riscvcard.pdf) from Patterson and Hennessy's RISC-V textbook ever since we switched from MIPS to RISC-V assembly in 2017. This semester, we've decided to make our own reference card from scratch to replace the existing green card. This should be the first in a series of posts documenting best practices we've learned from the process of building a reference card. It's still a work in progress, so feedback is welcome!

## Motivation

We had several reasons behind replacing the green card, from important accessibility concerns to smaller quality-of-life improvements:

- **Lack of text processing**: The old green card is scanned from a textbook, so you can't actually highlight the text for copy-pasting or use Ctrl+F to search for things. We'll probably devote a whole post to the accessibility concerns behind images of text, but one glaring weakness for everyone is that a reference sheet that can't actually be searched is lacking a pretty big feature.
- **Unfamiliar syntax**: The old green card describes functions in Verilog, which students aren't expected to know for this class. It's somewhat readable without knowing Verilog, but a lot of students have reported pretty much ignoring the description section, which loses a big part of the reference guide (knowing what each instruction does).
- **Extraneous information**: A substantial amount of this green card is material not covered in class, most notably all the extensions taking up the right half of the first page. The extra information leads to **small text** which students have reported as being an issue before.
- **Outdated information**: This green card is from 2018, and since then, conventions within our class and in the general community have changed. For example, we usually refer to SB-type instructions as B-type instructions in class now.
- **Obscure information**: The green card has some information that is technically present but difficult to uncover if you're just learning assembly for the first time. For example, I-type instructions are listed as having an immediate in the top 12 bits, but this is actually not true for right-shift immediate instructions, which use 7 bits for a funct7 code and 5 bits for the immediate (you can't shift more than 32 bits). This is vaguely presented in the green sheet, but it's quite easy to miss if you aren't actively looking for it, and it's led to student confusion in the past. This is a really specific example we found, but I think it's true in general that very condensed reference cards are sometimes not the best tool to start learning a language with.
- **Missing information**: 61C has other reference material that's often needed (e.g. ASCII table) that's not on this card, which often leads to us providing multiple reference cards throughout the class.

The biggest counterargument to all this is that despite the drawbacks, giving students access to a real-world reference card is a good way to give them hands-on experience from the start. This is a very valid point, and I do think there's value in presenting students with reference cards that aren't specifically tailored to the class. I'm definitely not opposed to having people use real-world reference cards in general, but this particular reference card was nearing end-of-life, and 61C's needs are quite specific so I haven't found a good real-world replacement. Ultimately, making a custom reference card seemed like the best short-term solution while we continue polishing other aspects of the class.


## RISC-V Reference, Draft 1

Our draft for now only inclues RISC-V reference material; additional material for other parts of the course will be built later.

The first draft was done in Google Docs by copying all the relevant information from the old green card into a new table of instructions. Then we transferred the tables to Google Slides (which we found worked better for manipulating layouts). Microsoft Publisher or Apple Pages are probably good tools to use too.

For now, we focused on a printable version since the midterm is coming up, but in the future we're hoping to work on a web-friendly version too.

Some design choices we made:

- **Length**: Fit all the RISC-V reference materials on a two-sided sheet. Keeping a reference sheet compact is nice design, and it makes using it on, say, exams a lot easier.
- **Avoid redundant information**: The original green card had two lists of all the instructions, arranged in a different order and with different information in each list. We merged that into one list.
- **Intuitive ordering**: We tried a few different orders (alphabetical, opcode, sort by type) but ultimately settled with following the order the instructions are presented in class, which does a nice job grouping similar instructions together.
- **Readable syntax**: We didn't want to use Verilog, but still had to pick a way to describe what each instruction does. We thought about writing out each instruction in C syntax, but that sometimes resulted in rather obscure C syntax that wasn't immediately readable. We eventually went with C-style pseudocode that used plain English whenever the pseudocode would be unclear. It's not the most formally correct, but it's good for learning, I think.
- **No footnotes**: I think adding footnotes opens a can of worms that eventually leads to exceptions and asterisks everywhere. We tried to design the reference sheet from the start so that any exceptions (like the special I-type instructions from earlier, which are now separated into their own subtype) are built into the sheet.
- **Technical rigor**: We debated on simplifying some out-of-scope material and presenting it in a slightly incorrect but more intuitive way, but ultimately decided that this is a reference sheet, so everything should be rigorously correct or not included at all. This actually led to a few points being left off the sheet, and led us to question why those "intuitive but technically incorrect" ideas were being presented in class anyway.
- **Minimize potential mistakes**: The old green card wrote that registers `x18` to `x27` are named `s2` to `s11`, which left you to manually count if you wanted to figure out the name of a register like `x24`. This isn't a difficult conversion, but it is prone to mistakes, so we ended up writing out a complete mapping of registers to names instead of abbreviating with ranges. Similarly, we added a blank space in between 7-digit binary opcodes (`000 0011` instead of `0000011`) to avoid transcription errors. We chose to write these in binary instead of hexadecimal since they're usually used in binary form, and writing them in hexadecimal might lead to errors when converting from hex to binary.

## Future Work

The immediate next step is making a printable reference for the other materials relevant in 61C (e.g. IEEE 754 floating point standard, ASCII table, SI prefixes).

Longer-term, I'd like to stop and think about aesthetic choices like fonts, shading, and layout. Compiling the sheet in LaTeX has also been floated around.

Finally, the long-term goal is to supplement the printable PDF version with a nice, searchable HTML web version that complements the PDF version. Incorporating student feedback as we go will be valuable as well, especially since we have the power to modify our own reference card however we like. Stay tuned for updates!

P.S. does anyone outside of RISC-V call their reference card a "green card" or "green sheet"? I haven't been able to find any other usage of this term.