---
title: Onboarding Concurrent Enrollment Students
tags: [start of semester]
description: 
author:
  name: Peyrin
  url: https://peyrin.github.io/
---

So, it turns out that writing a masters' thesis takes time away from writing blog posts. Who knew.

## What are concurrent enrollment students?

Concurrent enrollment students (abbreviated CE students for the rest of the post) sign up for classes through [UC Berkeley Extension](https://extension.berkeley.edu/). Sometimes these are students studying at other universities, or Berkeley alumni who want to come back and take another class.

One particularly common source of CE students is [the GLOBE program at Berkeley](https://globe.berkeley.edu/). I honestly don't know much about this program, except that it sends us a handful of CE students every semester, and that its students come from a group of pre-approved partner universities.

[Berkeley's Summer Sessions program](https://summer.berkeley.edu/) also allows non-Berkeley students to enroll in Berkeley classes over summer. I'm not sure if these students follow the exact same process as CE students, but the end result for course staff is pretty similar.


## Does CE require extra staff hours?

In my experience, in a large, scalable CS class, CE students don't require too many staff-hours compared to a Berkeley student. (There are still a few logistical hiccups that arise, though, which is what this post is for.) As long as we're clear about the prerequisites and requirements of the class upfront, students seem to do a pretty good job self-selecting into classes that they're qualified to take. CE students also seem to pick up on Berkeley's course platforms (e.g. Gradescope, Piazza/Ed, office hours queue) pretty naturally; in many semesters of taking on CE students, I've never really had to put in extra time explaining how a Berkeley CS class runs. Of course, I can't say that this will be true for all classes, or that there won't be exceptions to this.


## What's in it for Berkeley?

Setting aside the fact that CE programs give non-Berkeley students a chance to experience Berkeley CS, enrolling CE students has benefits for our classes and students too. CE students pay for classes by the unit, which means that CE programs usually generate revenue for the department (and therefore the university). This revenue can be used to alleviate some of Berkeley's CS funding problems; the extra money from CE students is sometimes used to expand Berkeley CS class capacities to hire more staff and enroll more Berkeley students from the waitlist.


## Enrolling CE students

CE students sometimes need to wait until the first or second week of classes before they receive approval from the department and the university to enroll in classes. This can create additional overhead for staff, who need to manage extensions to help CE students get caught up in the class, and for students, who need to catch up in the class. Also, I have no proof for this, but I suspect that some CE students will apply for a class and never hear back about how to enroll or start working on the class, which causes them to give up and withdraw their application.

CE applications are only visible by the instructor, so this fall is the first time I've actually been able to view them. [Here's a guide for how to find their applications and approve them.](https://sis.berkeley.edu/sites/default/files/how_to_approve_or_deny_a_concurrent_enrollment_application_instructors_ja.pdf) If you're not the instructor for the class, you'll probably want to bug the instructor early (before the semester) about this. In Fall 2022, the first wave of applications showed up for me on August 10, though the department didn't start approving applications until August 23 (the first week of classes).

The CE application portal UI is...not the best. In particular, there's no way to download a CSV or any reasonable list of students that we can use to build a roster. Here's a Python script that takes the raw text of the CE application portal and builds a CSV roster. To provide an input to the script, open the page listing all the applications, Ctrl+A and Ctrl+C to copy the raw text, and paste the text into a text file to pass into the script. (Credit to Nicholas Ngai for the script!)

```python
#!/usr/bin/env python3

import csv
from datetime import date
import re
import sys
from typing import Any

student_re = re.compile(r'(\d+)\s+Concurrent Enrollment Request\nName([^,]+),([^\n]+)\nSID(\d+)\nEmail:([^\n]+)\nBerkeley Status:([^\n]*)\nSubmission Date:(\d{4})-(\d{2})-(\d{2})')

# Get content.
with open('your-raw-text-dump-filename-here.txt') as f:
    text = f.read()

# Get all matches.
matches = student_re.findall(text)
rows: list[dict[str, Any]] = []
for m in matches:
    rows.append({
        'request_id': int(m[0]),
        'last_name': m[1],
        'first_name': m[2],
        'sid': int(m[3]),
        'email': m[4],
        'berkeley_status': m[5],
        'submission_date': date(int(m[6]), int(m[7]), int(m[8])),
    })

# Write CSV.
writer = csv.DictWriter(sys.stdout, ['request_id', 'last_name', 'first_name', 'sid', 'email', 'berkeley_status', 'submission_date'])
writer.writeheader()
writer.writerows(rows)
```

Once you've built a roster, you can add these students to all your course platforms (e.g. bCourses, Ed/Piazza, Gradescope) and maybe let them know that they can follow along with the class while waiting to be enrolled. This fall, I made announcements in the first two lectures about the status of CE students so that they knew about their application status.

A lot of CE students try to email the instructor directly, which is understandable. Sometimes this can lead to emails getting dropped, though, so getting a roster and reaching out proactively might be a more reliable way to reach out to all CE students.


## CE stats

In past semesters, we usually received around 10-20 CE students per semester, usually from the GLOBE program. I don't know if there were other CE applications I wasn't aware of, or if the program policy has changed since then.

In Fall 2022, as of August 15 (5 days after the applications opened), we had:
- CS 161: 71 concurrent enrollment applications, 21 listed GLOBE on the application
- CS 188: 106 concurrent enrollment applications, 25 listed GLOBE on the application

We don't know what the drop rate is like yet; we'll have to wait until the drop deadline later in September to see how many of the applicants are still on our roster.

Fun fact: The CE system sends me an email for every application submitted. Waking up to 150+ unread emails was not very fun.