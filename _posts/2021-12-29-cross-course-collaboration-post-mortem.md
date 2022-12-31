---
title: Cross-Course Collaboration Post-Mortem
tags: [cross course collaboration]
description: Collaboration efforts between two classes
author:
    name: Peyrin Kao
redirect_from: /cross-course-collaboration-post-mortem/
---

Official and unofficial collaboration between CS 161 and CS 61C produced some nice mutually beneficial effects for students and staff of both classes - hopefully other classes can use this as a model to facilitate more cross-course collaboration.

## Shared instructors

Nick Weaver co-teaching 161 and 61C this semester was a big help for putting this together. This is probably harder to come by for other classes but it’s not a necessity as most of the collaboration happens at the admin TA level. Having an instructor who’s taught both classes before does help though.

## Shared TA hires

Vron and I were both hired as 20h TAs for both classes (10h each). Officially the department doesn’t allow this but it should be fine if the instructors of both classes approve (Nick being instructor of both classes made this easy for us). It also helped that we are masters students in CS education so we have a research reason for getting involved in a second class (more data to collect).

This probably works best if the TA has a lot of teaching experience in one class (I’m a 7-time 161 TA and 2-time 161 head TA) and is adding on the second class. I was able to take a diminished role in 161 because we have other veteran TAs there who could fill the head TA position and other admin-level tasks. I highly doubt this works if the shared TA is still a head TA for one of the classes. Anecdotally it does seem like experienced TAs for one class moving to another class in one of their last semesters isn’t that uncommon, so that’s probably where to look for these types of shared roles.

This also works best if the shared TA mostly works on higher-level admin stuff instead of covering things that other TAs can do (e.g. discussions, office hours). Teaching a 161 discussion was definitely a time sink for me this semester even though I could teach discussion with no prep, and if I were to redo this semester I’d definitely skip over discussion for other logistics-level tasks. Vron had a similar experience teaching 61C lab. This also has the side benefit of not requiring as much knowledge of the newly added course’s material as an average TA (I only had to re-learn a subset of 61C content for this semester).

Do note that splitting time across two classes can be very time-intensive depending on how much time you put into each class. A better model might be for an experienced TA to move full-time to a different class and unofficially keep in touch with the original class in an advisory role. (We’re trying this next semester with me at 61C full-time so we’ll see how that goes.)

## Shared infrastructure

Being on staff for two classes almost immediately makes you realize how much recycled or redundant infrastructure exists between the two classes. Consolidating infrastructure is nice because each class only needs to support upkeep for half of the infrastructure used, while relying on the other class to support upkeep for the other half. Examples we caught this semester:
161 moved to using Github Classroom after investigating 61C’s experiences with it, and 161 is probably going to borrow 61C’s Galloc webapp for making Github Classroom repos (apparently Classroom is bad at supporting Berkeley-sized classes).
161 and 61C have duplicate grading scripts (Python-to-Gradescope for 161, JS webapp for 61C). We’re probably consolidating to one grading script in spring to avoid double upkeep.
61C was able to borrow the extensions backend (form, spreadsheet) from 161.
61C was able to borrow the incomplete processing backend and overall process (check-in emails, progress reports, grading across semesters with inconsistent grading structures, etc.) from 161.
61C borrowed 161’s LaTeX exam template to make an in-person exam.
There were also cases where both classes needed something new developed this semester and we were able to collaborate and make it once instead of redoing the work. Hybrid exam infrastructure was probably the best example of this.

Documentation for more of this stuff should be coming next semester.

## Shared TA staffing

There aren’t many cases where sharing other TAs between the two classes is too helpful, but it can definitely help when you need extra manpower from trusted people that doesn’t involve knowledge of course material.

The most obvious case of this for us was exam proctoring - 161 was very short on proctors for the final (campus gave 161 a lot of small classrooms) so we were able to borrow proctors from 61C. We didn’t need them to understand any 161 content to proctor the exams - they just helped monitor students, keep track of people using the bathroom, and collect and count exams at the end. We paired each 61C borrowed proctor with a 161 proctor which freed up the 161 proctor to answer clarification questions.

The nice thing about proctor exchange on the final exam in particular is that some TAs can’t make their class’s exam time, but can make the other class’s exam time, so even if there isn’t a need to mass donate proctors from one class to another, this facilitates a nice exchange so that both classes can be adequately staffed while giving TAs a bit more flexibility over when they’re needed to proctor.

The other nice thing about collaborative proctoring is that we can actually use it to staff exams for both classes at the same time. Some 161 alternate finals were scheduled to coincide with the 61C final, so we just had 61C proctors handle those (in a separate room with 161 clarifications projected instead of 61C clarifications). This could probably be extended to a room where students from both classes are taking alternate exams, with clarifications/timers for both classes projected at the same time.

Other potential use cases for shared TA staffing: exam scanning and grading, printing discussion worksheets, etc. We can definitely get more creative with this once ties are established between classes.

## Maintaining TA pipelines

I have to do more research into this, but it seems like with classes like 61C that alternate between large semesters and smaller semesters, when the class switches into its smaller phase, a lot of TAs in the pipeline are lost from being unable to be rehired. (Anecdotally, many find tutor roles or other ways to stay involved like CSM, but it seems not everyone can always stick around.) Next semester, 161 is going to take on 4 or 5 ex-61C TAs, which will be nice for strengthening ties between the two classes and keeping TA pipelines intact. We’ll see how well this works out if those TAs ever come back to 61C or otherwise contribute to shared knowledge between the two classes, but just switching staff between two classes seems like a good way to spread best practices among different staff.

## Shared course materials

61C is a prerequisite for 161, so collaboration between the two classes also has a benefit in more seamlessly connecting content between the two classes. To give an example specific to these two classes, 161 has been teaching x86 calling convention in sort of its own in-house developed way, but having spent a semester at 61C, I now have a much better understanding of how 61C students see calling convention (though in RISC-V instead), and I’m probably going to adapt 161 course material at some point to leverage that understanding better.

## Less duplication of Student Support

> This section is written by Vron, who managed student support for both classes in Fall 2021.

For students concurrently taking CS61C and CS161, the time and energy students and course staff spent on student support was effectively halved. I was able to take one conversation with a student in one course and correlate it with data or context from the other. A hospitalized student who needed to submit detailed documentation in order to get a no-proctoring exam accommodation only needed to do so once for all four of our exams. Multiple students navigating incompletes in either or both classes only had to go over details with me once. EECS and CS Students starting into the major who need to take CS61C are often not connected to the necessary resources on campus. This experience helped me realize that the majority of students who struggle in CS161 are actually primarily struggling in CS61C, and the load of our lower division CS courses has a ripple effect throughout the department. Students also only had to learn one system and set of policies to interact with both courses. Standardizing student support through both courses had huge positive impacts on these dual-enrolled students.

## Other/conclusion

There are a lot of intangibles associated with splitting time between two classes and trying to establish long-term ties between the two classes, but hopefully I put down some immediately actionable things that other pairs of classes can try out. This is definitely an ongoing project as 161 and 61C are continuing collaboration next semester for hopefully a long-lasting partnership even after this current crop of TAs graduate, and hopefully we can document how it goes for others to follow in the same model.
