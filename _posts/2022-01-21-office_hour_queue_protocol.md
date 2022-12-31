---
title: Office Hour Queue Protocol
created: 2021-01-21T23:08:00.00
modified: 2021-01-21T23:08:00.00
tags: [office hours]
description: Onboarding staff for office hours queue infrastructure and general starting guidelines
author:
    name: Caroline Liu
redirect_from: /office_hour_queue_protocol/
---

## Setting up office hour queues

Using the office hours queue can be intimidating, especially for those who've never seen it from the staff side before. But it doesn't have to be! There are a few features to keep an eye out for from the get-go.

Usually, your class will provide some sort of guideline as to how office hours will operate. This should cover where your office hours will take place as well as some general rules of thumb in taking tickets. We'll talk about a few general guidelines below for how to help make sure office hours run smoothly!

As we're still operating in year 3 of COVID, it's very normal to have hybrid office hours, split between classrooms and Zoom links (or Discord). If a class you're teaching doesn't office online support, it may be something worth exploring with course staff, as there are many students who benefit from remote support, both during non-COVID and COVID times (but that's a discussion for another post).

If you navigate to your class' office hour queue, typically https://oh.\<course\_name\>.org, you'll be asked to log in and authenticate via OkPy. As staff, you'll notice after you log in that you see more options than you would as a student, namely the Activity Log, Admin Panel, and when you click the dropdown with your name, an Online Setup option. If you're unable to log in or if you don't see these options, you should contact staff in charge of your course's infrastructure as it's likely the roster hasn't been updated yet.

Class head of staff, typically head TAs will usually be in charge of handling the options under Admin, as it handles the different ways the office hours queue can be used. If you haven't explicitly been told to alter something in that panel, you shouldn't as it could change queue behaviour. Walking through what exists in that panel, general features include queue status switches, with some of the important ones detailed below:

- **Should the queue be open to new tickets?** This should be set by default to "Closed", as students should not be able to make tickets willy nilly. The TA in charge of the first office hours (OH) of the day, or OH chunk, should toggle this to "Open" when their OHs start. Subsequently, the last TA of a chunk of OHs or of the day, should toggle the switch back to being closed. Not doing this can cause tickets to pile up, that eventually have to be either cleared by TAs taking old tickets or by "nuking the queue" (clearing all the tickets without taking any). The latter can cause rampant student disappointment and questions.
- **Should only students ont he roster be allowed to log in?** This toggle should be set by default to "yes". This is because otherwise, anyone with a valid OkPy login can access your course queue.
- **Should the queue show the estimated wait time and online staff members?** This has been a point of contention between course staff members but overall, it lets students know the approximate wait time until their ticket might be helped. In the past, when queues were busier, sometimes the wait time would be marked as being 8+ hours, and it upset students for various reasons. It's traditionally used as a measure of how quickly a queue is being filled up and if there is enough staff on board for support. It's up to the course as to whether it's on or not, but it's worth discussing.
- **Welcome Message (supports Markdown)** This should be set for every class and customised to how students should use the office hour queue in the class. Some good points to mention would be how to join a call or to get help, office hour ticket format, and what is expected out of a student before or during requests for help.
- **Ticket Prompt (supports Markdown)** This should be filled with any information staff wants to remind students about prior to making a ticket.

The other tabs under "Admin" can be ignored by most staff members.

The activity log itself typically can be left alone, but here you can view past tickets you (and other staff) have taken. It can be useful if you need to reference past students helped to track hours or to answer Piazza questions, for instance.

## Online setup

Having the correct online setup is important for students to know where to go to receive help. For in-person office hours, typically course admin will have set the respective rooms used for office hours, and staff can just take tickets based off of what their class policy is, whether that be the first for their room or first off the queue.

For remote office hours, staff will have to provide the link to the Zoom room their office hours will be held in. Some courses have staff provide their own personal links and others will have a set of shared Zoom links but your course should tell you which link to provide. After you put this in the "Your Default Video Link" input, and take a ticket, the student will be able to join the call through the "Join Call" button.

Sometimes, classes will have a "shared document" which students will be able to access through their ticket if necessary, but often times students will provide their own documents, or find annotation directly on the screen to be more useful. However, if you find a shared document works better for your teaching style, feel free to put the link in the shared document slot, and students will be able to access it!

## Navigating the queue

As staff, your general sphere of influence should be in your online setup, detailed early, and the queue itself. When the queue is opened, you'll be able to see when students make tickets. They'll stack in first-come-first-serve order, and you'll be able to see their ticket title and general description before accepting the ticket. Note that you will **not** be able to see the name of the student prior to accepting the ticket. This is to avoid any potential biases against, or towards, certain students.\*

Once you click on a ticket, you'll be given the option to accept it, which you can do by clicking the blue "Help" button. On the student side, they'll now be able to see that you've started helping them, and can either join your physical room or join your call.

If you find the student isn't joining, you can message them in the chat on their ticket page. This chat will persist until the ticket is resolved.

Sometimes, you might need to put a student on hold. This can be done with the yellow "Come Back Later" button on the ticket. Some common reasons that you may want to put a student on hold include:

- The student is currently not responding. In these instances, you should not resolve their ticket. The student may've popped away to eat, drink, use the restroom, or simply, to take a break from being at their computer, These are **all** valid reasons, and the student should not be penalised for not being available exactly when you take their ticket. A good rule of thumb here would be to keep the ticket not resolved unless your office hours are over and you are the last staff in your block of office hours.
- The student needs to quickly do something on their end. This is extremely common; sometimes a student will come in with a bug they can't resolve because they maybe can't compile their code, or has a glaringly obvious bug (to staff), and it's something that can be resolved quickly, or maybe they have a technology issue. These kinds of issues are usually quick to solve, but they're not always fully beneficial to a student when there's a long queue because they may run into a bug right after, but because the issue they came in with was resolved, they'll have to requeue themselves and wait for longer. Similarly, if they're having trouble with their machine or a technology issue, it's unfair to ask them to requeue and wait. In these circumstances, it's good to put the student on hold, and once they resolve their more superficial issue, to re-request help. **This can be done after a certain timeout, approximately 10 minutes, from the student's end** or the staff member can resume helping the student before then manually.
- A student is spamming tickets and taking priority over other students. These instances should be noted and the purpose of putting these students on hold is so that their disruptive behaviour affects other students seeking genuine help less.

There may be other reasons, but these are some general ones to get you started!

There is also a "Requeue" button on the ticket. This should generally not get used. This is because requeuing puts the student that you just helped back at the top of the queue, and if this is done enough, it means the queue never moves. If you feel like you need to requeue a student, put them on hold instead.

When you're finished helping a student, you can resolve the ticket by clicking the "Resolve" button.

If you're the last staff member with office hours during a block, you also have the option to delete all tickets from the main queue page. This should be done with care and discretion as there are instances when you may not want to clear all existing tickets immediately when closing the queue. If you're not sure, consult other staff members.

## Guidelines for those new at office hours

Managing office hours can be intimidating and often difficult. Here are a few good techniques to keep in mind when taking tickets:

- If there are many conceptual questions or questions about the same problem, say on a lab or project, take them all at once! There is no real reason questions that don't require students to share code can't be taken together.
- If you're in-person, encourage students waiting to work together; often times, they'll make a lot of progress before you've had a chance to help them. This can be more difficult in online situations, but it can still be encouraged, and if students feel more comfortable talking in a separate room, you can create breakout rooms and participates can self-select into their preferred rooms.
- Stay within the ticket length limit. Different courses have different policies surrounding this, but a pretty standard debugging ticket limit would be somewhere between 8-13 minutes.
- Follow the priority of tickets for your class. This may just be first-come-first-serve, but some classes may have different types of office hours and thus, prioritise different kinds of tickets. Staying within those bounds can help make your experience more managable.

More tips on managing office hours queues can be found [here](https://pedagogy.cs161.org/notes-on-office-hour-queues/).

## Closing Words

As a general rule of thumb, if you aren't sure about something, ask! Your fellow course staff members are there to help you, whether you're a new academic intern who's never taught before or a seasoned TA. Everyone's questions are valid, and if you can't help a student, don't beat yourself up over it. Two methods I've found to be useful are first pinging Slack (or whatever other communication platform your course uses) to see if anyone else has suggestions, and if not, to direct the student to Piazza or Ed, whichever the course uses. I also like to have the student email me their corresponding post afterwards, so I can keep track of which students I directed there so I can help them better.

A lot of the time, office hours can feel like guess-work, and that's okay. Students come in sometimes with the wackiest bugs that even long-time TAs haven't seen, so it's perfectly normal to not always know the right answer.

With that being said, happy office hour-ing!


\* In the past, there've been instances of certain students harrassing or targeting specific TAs, for various reasons, as well as students with problematic behaviour. If you notice a student behaving with bias or poorly, whether it be towards you or other staff, you should report that to other course staff in an appropriate manner. There are also instances of students spamming the queue with tickets (this is more of an issue if students are allowed to make one ticket at a time), but if you do notice this, it's okay to let the student know that isn't okay and to put them on hold.
