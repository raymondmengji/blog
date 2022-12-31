---
title: Setting up 61A's OH Queue
tags: [start of semester]
description: 
author:
  name: Peyrin
  url: https://peyrin.github.io/
---

## Set up okpy

OH queue pulls its roster from okpy, so you need to first set up an okpy instance for your class.

1. Visit [https://okpy.org/](https://okpy.org/) and sign in.

2. You should see a list of classes. See if someone's already created a class for your semester.

    ![List of classes on okpy](/assets/posts/2022-09-02-setting-up-oh-queue/oh-queue-setup-1.png)

3. If you don't see your class, then visit [https://okpy.org/admin/course/new](https://okpy.org/admin/course/new) to create a new class.

    ![New class setup on okpy](/assets/posts/2022-09-02-setting-up-oh-queue/oh-queue-setup-2.png)

    Make a note of the "Offering" tag you use here (following the pattern in their example should be fine).


## Enroll staff in okpy

To give your staff admin access to the queue, they need to be registered as staff in the okpy class.

{:start="4"}
4. Back on the okpy homepage, click on your class.

    ![Class homepage on okpy](/assets/posts/2022-09-02-setting-up-oh-queue/oh-queue-setup-3.png)

5. Click on "Enrollment" in the left sidebar.

    ![Class homepage on okpy](/assets/posts/2022-09-02-setting-up-oh-queue/oh-queue-setup-4.png)

6. In the "Batch Enroll" section on the right sidebar, click the "Enroll from CSV" option and add all your TAs.

    ![Enrollment page on okpy](/assets/posts/2022-09-02-setting-up-oh-queue/oh-queue-setup-5.png)

    You can leave the Course Login and Section fields of the CSV blank, but the CSV expects blank strings for these two fields. For example, you must have the extra comma at the end of: `evanbot@berkeley.edu,EvanBot,12345,,`

    Adding as Instructor, Teaching Assistant, Reader, or Lab Assistant should all be sufficient to give staff access to the OH Queue. I don't think they make any real difference in terms of OH Queue permissions.


## Enroll students in okpy

Optionally, if you want to restrict your OH queue to only be accessible by students, you can register all the students in the okpy class. Note that this also means you have to sync the okpy roster periodically, which involves extra overhead.

The simplest way to enroll students is probably to sync with bCourses, which is what we show here. You can probably also manually enroll (using the same steps for enrolling staff, but adding as Student) if you want.

{:start="7"}
7. Back on the okpy homepage, click on your class again. Click on "bCourses" in the left sidebar.

    ![bCourses page on okpy](/assets/posts/2022-09-02-setting-up-oh-queue/oh-queue-setup-6.png)

    Fill out the fields to connect your okpy class to bCourses. You will probably need to visit your bCourses class to get the URL and create a new access token.

8. Click "Enroll Students from bCourses".


## Set up OH Queue

Finally, you have to set up the OH queue for your class to point at the new okpy class you made. This section assumes that you already have an existing OH queue made for your class; if not, contact 61A staff.

{:start="9"}
9. Visit [https://auth.cs61a.org](https://auth.cs61a.org). You should be redirected to an OKPy login.

10. At this point, you should see a section of config for your class like this:

    ![CS 161 config section on auth.cs61a.org](/assets/posts/2022-09-02-setting-up-oh-queue/oh-queue-setup-7.png)

    If you don't see this section, you have to ask a head TA from a previous semester to add your email as a course administrator, or ask 61A staff to add you.

11. Under "Set new endpoint", enter the new okpy endpoint (recall the "Offering" tag from before; also can be found on the okpy homepage).

12. Check that your new TAs can log into the OH Queue as staff. Newly-added TAs may need to log out and log back in again before their staff access appears.


## Setup hack: use the same class every semester

A lot of Berkeley CS classes don't use okpy for students anymore. The least reliable step of this process is passing 61A auth admin access to new head TAs every semester (the "Set up OH Queue" section). One way to make this process more robust is to create a dummy okpy class that only enrolls the TAs for every semester, and always have the OH Queue pointing at that dummy okpy class. 

CS 161 has a dummy okpy classes `cal/cs161/fa00` that only enrolls the current semester's TAs. With this dummy class, you only need to do the "Enroll staff in okpy" section of the setup here to update the staff roster.

If you don't have students enrolled in your okpy class, be sure to go to your OH Queue, click on "Admin", and set "Should only students on the roster be allowed to log in?" to "No" so that students who are not in your okpy class can stil make tickets.

![OH Queue admin settings](/assets/posts/2022-09-02-setting-up-oh-queue/oh-queue-setup-8.png)