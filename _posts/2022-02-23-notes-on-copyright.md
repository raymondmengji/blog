---
title: "A Guide to Navigating Take-downs"
tags: [copyright, dmca, git, chegg, coursehero]
description: How to have your solutions removed from the internet
author:
    name: Zephyr Barkan
redirect_from: /notes-on-copyright/
---

Our course content does not hold the same weight and meaning when the solutions are publicly available on the internet. It is cheaper to put resources into DMCA take-downs rather than to hire the required staff to rewrite, debug, and test a new suite of assignments every semester.

So how to we get our solutions removed from the internet? I was peeved Summer 2020 that no one had an answer for me and went on a journey that ended in central campus' lawyer's zoom room (if you're reading this, thank you).

## Getting Approval

Before submitting any DMCA take-down, you must have written approval (or clear proof of a "good faith" attempt) from all copyright owners. This will be anyone who wrote or substantially edited the assignment. In Summer 2020, this is the email I sent:

> “Hello everyone,
> I have been putting a lot of effort into pursuing a DMCA take-down for several public 61B(L) solutions repositories. In order for me to proceed, I will need to act "on behalf of the copyright owners," which would be all instructors who have edited and/or created these assignments. The only actions that would be taken on your behalf are removing or making private such repositories.
> Please let me know if you would like to discuss this further!”

Save any and all responses from the copyright holders. Save **all** documentation. This is very important. Invalid DMCA take-down notices are **perjury**. You (the person submitting the take-down) are legally liable for the validity of the request.

## Removing things from GitHub

### Evidence

Gather all of your evidence. This will include **all** documents containing the original copyrighted material.
Gather a list of all of the repositories you want removed. If the repository contains non copyrighted material, you have to record the specific url of every file you want removed. You should also check for forks etc, as GitHub will **not** do this themselves. 
Attempt to contact every owner **before** submitting the DMCA take-down. You may warn them that you will submit a DMCA take-down after some number of days if they do not respond to your email or remove (delete or make private) the repository.

### Language

You **must** start with the sentence “I have read and understand GitHub’s Guide to Filing a DMCA Notice.” without modification. 

Ensure that you clarify that you have the entire copyright over the assignment **and** associated solutions. “As a department, we own not just the skeleton files but the solutions themselves. The
skeleton files, solutions, specifications, graders, and introductory material have all been
authored by the department and are our sole property.”

If GitHub's lawyers complain that the student who completed the assignment has copyright of their solution due to their efforts, then specify that it is a derivative work and thus that you retain ownership of the copyrighted material.

Additionally, I strongly recommend referring to their "safe harbor protections." Specifically, I say:

> I am writing to you concerning the unauthorized reproduction, display or other use of
> those copyrighted works on the site.  I have not granted permission or license for you to
> post or otherwise use those materials.
> 
> Pursuant to 17 U.S.C. § 512(c)(3)(A), please immediately and permanently remove or
> disable access to the following items: ...

If they do not "immediately and permanently remove or disable access" to the content in question, they risk their "safe harbor protection" under the law. This means that they would be held liable for the content their creators are hosting on their website. This would very very very VERY expensive for them, and thus this is a great final threat if needed. For more, look into the ramifications of FOSTA/CESTA.

For an example of the entire form, with language, look [here](https://drive.google.com/file/d/1EpMV8I4x3OMg0yxRKaWGuAAuTd18UbNN/view?usp=sharing).

### Submitting

1. Submit the form which can be found here: [DMCA take-down notice](https://support.github.com/contact/dmca-takedown)
2. Save the above form as a PDF and email it to copyright@github.com

## CourseHero and Chegg

Use the following sentence in the header or footer of all course materials: **“This content is protected and may not be shared, uploaded, or distributed.”**  Course Hero has personally assured me that that their filtering tool will, in nearly all instances, prevent the upload of documents containing the above phrase.

Chegg is currently working on a similar feature.

If it comes to it, you can utilize similar language as with GitHub above (about copyright ownership and safe harbor protections specifically) to request CourseHero or Chegg remove any specific content. If you do so, Chegg should be able to confirm which users accessed any content before it was removed from the website.