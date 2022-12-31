---
title: Notes on Office Hour Queues
created: 2021-01-14T20:13:18.54
modified: 2021-01-14T01:37:28.20
tags: [office hours]
description: What to do when queues get long, and how to avoid long queues
author:
    name: Peyrin Kao
redirect_from: /notes-on-office-hour-queues/
---

## Triaging long queues

You show up at office hours and there are dozens of people waiting for help. Some have been waiting for hours. How do you get the situation under control?

- **Limit the time spent on each student**: Tell students that a lot of other people are waiting, and out of fairness, you can only spend a few minutes (5-15 depending on queue length) with their ticket. I find that students are usually pretty understanding when you explain it this way. See the next section for how to make the most of a short amount of time.
- **Help students in groups**: If you see multiple people need help on the same question, group them together and talk through conceptual help with all of them. If you spend 20 minutes helping 5 students together, that comes out to 4 minutes per student - pretty efficient! This is most helpful when students need conceptual help, but probably less useful if everyone wants individualized debugging help.
- **Create an impromptu project party**: When the queue is so long you're pretty sure you won't be able to help everyone in time, it may be better for everyone to convert office hours into a large project party, where students are given more free rein to help one another, and you do your best going through as many help tickets as possible. When this happened for a long remote office hours queue, we got everyone in one large Zoom call and worked through tickets out-of-order based on whatever was easiest to debug in hopes of covering as many students as possible.


## Effective short tickets

The queue is long and you're pretty sure you can't spend more than a few minutes per student. How do you get through students quickly while actually providing help?

- **Always leave students with something actionable**: If you give the student a concrete set of next steps, that gives them something to do while you work on other tickets to get the queue under control. Students probably don't feel great if they've waited for a long time and they end up just as stuck as before they made the ticket. Examples of concrete action items are a debugging strategy (set a breakpoint here and make sure all the arguments to the function are correct), referencing a specific piece of course material for them to review (e.g. a lecture or discussion), or trying to write a certain implementation differently (e.g. rewrite this function to use a linked list instead of a hash map).
- **Reiterate that they can keep asking for help**: I always tell students at the end of the ticket that if they still have questions, they can rejoin the queue or make a post on Piazza that I'll look at later. I think people are more understanding of a shorter help ticket if they know that they can get more help later, as opposed to thinking that this help session is the last piece of advice they'll get.
- **Come back later**: As a combination of the above two ideas, you can give people an actionable item and then tell them you'll check back in a few minutes to see if they made any progress or have any other questions. In the best case, the student follows your advice and solves their problem, which means you successfully helped them in a short amount of time. In the worst case, the student needs more help, so you can repeat the process of giving them more action items or walk them through something confusing. Giving yourself 10 minutes in between gives you time to work on other tickets. You can also use that time to maybe play around with their code yourself to see if you can spot the mistake more clearly. Students are also more inclined to actually follow your action items if you say you'll come back, because if they don't follow your advice, you won't have any new advice for them when you return.
- **Don't spend too much time on one debugging session**: If you can't spot the error right away, and you can't get it after a few minutes of looking around, it may be better to ask someone else to take a look, or redirect the student to Piazza for later. Depending on the project, it's very possible the student has a really subtle bug that's incredibly hard to spot live, and it's not a good use of office hours to spend too long trying to find it with the student. If the student isn't learning anything and you're just staring at their project silently or telling them what to do, that's not a great use of office hours.

It's worth noting that short tickets aren't always the ideal way to move through office hours. In particular, you probably want to watch out for thrashing, where a student has a conceptual misunderstanding that takes longer to explain, but because they're being rushed through office hours, no individual ticket ever helps them entirely, causing them to keep coming back with the same misconception. It might be better to invest 20 minutes with this student now, rather than have them come back repeatedly for a bunch of 5-minute sessions. This is kind of a judgment call depending on what exactly the misconception is, though.


## Plan for long queues

Long queues around project deadlines are usually predictable. Instead of dealing with emergency triage when they happen, it's a lot better for everyone if you plan for them in advance.

- **Stack office hours near deadlines**: Have multiple TAs staff every office hours slot when it's getting close to the deadline. In particular, it helps to stack the beginning of any OH block, when a flood of people join the queue, and the end of the OH block, when you have to move quickly to clear the queue. As much as we try to make people start projects before the deadline, it's an unfortunate reality that most people work near the deadline, so we should embrace that and plan for it in advance instead of being surprised by it.
- **Reallocate staff hours to extra office hours**: The quality of office hours support (i.e. queue length) is a big contributor to overall student satisfaction with the course (learning experience, stress levels, etc.), and it may be worth sacrificing other parts of the class for extra OH support. In particular, 161 has had good success decreasing the number of discussions (which are usually not too heavily-trafficked) and reallocating those hours to extra OH support. In weeks when OH are expected to be heavy, it may also be worth diverting hours from backend dev tasks (e.g. developing new projects, exam writing, etc.) if possible.
- **Allocate extra hours to clearing the queue at the end**: I haven't tried this before but I think it's worth trying out. When you know that the queue is not going to be cleared at the end of an OH block, it might be worth assigning a TA to be there for an hour after the queue closes just to clear out any remaining tickets (not taking any new tickets). One challenge is deciding when this is necessary, but if you're sure that OH will be overloaded in a given week, this is probably worth trying. It also helps avoid staff overwork: no one is obligated to stay extra hours, and no one has to make the choice between volunteering extra time or abandoning students still on the queue.
- **Keep staff hours flexible**: When allocating staff hours at the beginning of the semester, leave some slack that can be used when office hours get unexpectedly busy. This semester in 61C I'm going to try and do "swing office hours," which means I have no set OH times, but I'll monitor the queue and hop on whenever it gets busy. I doubt many TAs have a schedule flexible enough to do this, though. Even if most classes can't have fully flexible swing TAs, having TAs available on call to cover when things get too hectic is very helpful.


## Conceptual vs. debugging tickets

This has been tried in 161 for a few semesters with pretty good success, and it's being tried in 61C in Spring 2022. The idea is to have students identify their ticket as either conceptual or debugging.

Conceptual tickets are used if the student doesn't need staff to look at their code. This means staff can dequeue groups of students at a time for better efficiency. Staff don't need to repeat the same explanations for multiple students, and students can listen in on questions that their peers have. Students choosing this option can't have their code looked at individually, but they'll likely be helped faster.

Debugging tickets are used if the student needs staff to look at their code individually. These tickets have to be processed one at a time, so if the queue is long, they may need to be limited to a few minutes each. Students choosing this option get one-on-one help, but may need to wait longer and get less time with the TA.

The main problem is students really don't get how to self-sort into each type of ticket. Sometimes a student thinks their ticket is debugging, but they actually have a conceptual misunderstanding that takes longer to explain. Other times, a student just doesn't read the description and puts down "conceptual" when they actually wanted someone to look at their code. I usually ask that student to stay after the other students leave to give their code a quick look.


## Long-term work: Shortening queues

Long-term work should focus on addressing the root causes of long OH queues.

- **Cause**: Project specs aren't sufficiently detailed about common mistakes, so students flood OH with repetitive questions.<br>**Solution**: Add more details in the spec about common mistakes and misconceptions.
- **Cause:** Students don't feel comfortable using available debugging tools.<br>**Solution:** Release additional course materials (e.g. videos, readings, guides, smaller lab assignments) to get students more familiar with the tools they should be using on their own.
- **Cause:** Staff (especially newer TAs and tutors) are inexperienced at finding common mistakes or debugging the project.<br>**Solution:** Make debugging guides for staff.
- **Cause:** The project is really hard to debug for staff. As a concrete example, 61C's autograders have "comprehensive tests" that produce no meaningful output when they fail, which leaves students and staff confused as to where the problem is.<br>**Solution:** Refactor projects so that pinpointing mistakes is easier.

Improving the project experience for students is a much larger problem than managing long OH queues, so I'll save more discussion on this for a later post.