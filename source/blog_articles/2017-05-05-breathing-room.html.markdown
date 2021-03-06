---
title: Breathing Room
date: 2017-05-05
tags: edX, MOOC, planning poker, bootcamp, volunteers
author: Sam Joseph
---

![breathe](/images/breathe.jpg)

I felt like I was in a bit of pressure cooker yesterday with so many different tasks piling up.  I've managed to relieve the pressure slighlty by requesting that the start date of the edX MOOC get put back by a week.  UCBerkeley and edX seem just fine with that, and it's done, and it brings the operation of the TA training course AV102 into line so that the TAs can help with the review of the course material.  This was the mistake that I made last year--that the final assigninment in the main 4 week body of the AV102 course is pair programming and it's in the following week that the learners start getting credit for contributing to supporting learners in the main MOOC and reviewing the course material.  I think part of the key problem, and probably the reason I made the SAME mistake this year (despite trying hard not too) is that my schedule spreadsheet didn't include the fourth assignment and the first level 2 certificate items for the AV102, screwing up my estimates for when that course ends.  So I've fixed that now, and hopefully I can avoid the same mistake again, although I'm not sure how many times we'll be running this course again in this form.

It's been nice to meet learners from the course coming into the AgileVentures hangouts this week.  I've had them participating in votes on the LocalSupport project, which is probably a good learning experience for them, but other LocalSupport contributors haven't been around.  I think the voting on stories makes a lot more sense for people who are maintaining a certain level of involvement with the project, naturally; which turns me back to thinking that the bootcamp model has a lot going for it in that respect.  Not that I ever saw creating user stories or voting on them in any bootcamp I've been involved with, but the opportunity is there.  I think the difficulty is that both for the individual learner and the project outcomes you need a certain base level of commitment; a certain number of hours a week that are going into the coding and project managment.  That's really difficult to get from a group of volunteers.

Most of the recent regulars in LocalSupport don't usually make the kick-offs, which have been quite well attended by Sigu, Cess and Stella, but they weren't around yesterday.  Admittedly it was the first time we moved it to Thursday.  Michael showed up and we talked about the direction of the overall project and the apparent low use of the system.  We spent 45 minutes chewing the fat, and I'm not sure how much we achieved, apart from me bringing Michael up to date with how the project has pivoted from being a directory of organisations to focusing on listing volunteer opportunities.  I'm not sure it was a very productive discussion.  Maybe I should have been doing more listening.  I have trouble when I'm in the pressure cooker and I think people are telling me things I already know.  Then again, maybe it's more important to allow someone to express what they want to say.  Michael was telling me I had to understand that lots of MOOC participants are just taking MOOCs to blast through 30 MOOCs in a year, just get a taste of things.  Totally.  Lots of people are just looking to get a taster of what's going on in a particular subject area; and I do feel pleased that the AV folks can get to participate in scrums and vote on stories.

More the difficulty for me is that I'm behind on reviewing the PRs for LocalSupport and regular meetings with the client have gone out of the window with my overload on the NHS wiki project.  That could change in a week or two, but realistically I have to work on things that will pay for my time, as I'm out of spare cash.  I can see what I think would help the LocalSupport project thrive, i.e. active reviewing and integration of pull requests.  After meeting with Michael I did spend some time reviewing and see to my pleasure that Marouen had been reviewing and giving feedback on several open PRs.  That leaves Marouen's Pull Request which needs a detailed review and then some planning activity; but I don't think I can devote time to that unless there's some sort of funding for it.  I did manage to get Zmago's new ReachSkills volunteer integration out, and we could have that onto production soon.  That's the new vision for the site, that if the site were a one-stop shop for all the different sources of volunteering opportunities in Harrow then that might give people a reason to visit it regularly.

To be honest I think part of the problem is that the project hasn't included us meeting and interacting with the intended end users.  At least in the NHS wiki project I've been out to talk and interact with lots of different key stakeholders.  The LocalSupport client is in contact with lots of different charity groups in Harrow, but it feels like we're just guessing about what the Harrow voluntary sector might actually want.  It's like we've spent nearly five years doing what design sprints are supposed to help us avoid, i.e. we keep building different versions of a full system, to discover that people aren't so interested.  Not that we haven't had lots of great learning experiences along the way for the client, for me, and for the different folks in AgileVentures who are contributing.  That said maybe recently I've drunk too much design sprint Kool-Aid, and I'm starting to see the need for them everywhere.

In the NHS wiki project we haven't had any money or resources for development, but we've substituted off-the-shelf platforms, and we're doing high level usability tweaking much faster and getting quick feedback through testing with stakeholders.  I think that's the kind of thing that we need to supercharge our AgileVenture projects.  Of course I'm supposed to be turning myself from a hero to a host and not driving adoption of these things.  The AV community has been coming up with their own ideas and have arranged a meeting for next Monday where I think it's important I take a back seat and allow others to craft ideas, and then help empower them to try them out, fail and reflect and improve.

Gosh, well this blog went off in a different direction than expected.  I was planning to focus on how most of yesterday morning was spent on configuring SSL certificates on Apache in our Bitnami/Azure setup and how I was just about to give up and then it started working after this incantation:

```
./letsencrypt-auto --apache --apache-server-root /opt/bitnami/apache2 --apache-challenge-location /opt/bitnami/apache2 --apache-handle-sites FALSE --apache-vhost-root /opt/bitnami/apache2/conf/bitnami -d <domain-name>
```

Although I did also have to set up `sites-enabled` and `sites-available` directories with symlinks like so:

```
ln -s /opt/bitnami/apache2/conf/bitnami/bitnami.conf /opt/bitnami/apache2/sites-available/<domain-name>.conf
ln -s /opt/bitnami/apache2/conf/bitnami/bitnami.conf /opt/bitnami/apache2/sites-enabled/<domain-name>.conf
```

And it also involved splitting the VirtualHosts files up, and then merging them back together after the SSL cert was installed, in order to get the redirect from http to https working properly.  That was pretty much the soft launch of https://wiki.healthylondon.org but there are so many other things to tidy up.  I may live to regret that we are hosting the wiki ourselves.  I feel like I'm back in the early 2000's managing `LocalSettings.php` and `apache.conf`, but it seemed the only way to get the thing set up on schedule.  Go with the flow!  I worry slightly that this will bite me when we need to renew the certificates as I'll have to decompose the VirtualHosts file, but then again, maybe the auto certbot will be able to handle that then.  One thing at a time!

At least with the MOOC put back a week I feel like I have space to implement some delegation in AgileVentures, finish up this round of the NHS wiki project, and get the MOOC prep done.  I've managed to create just a little breathing room ...

### Related Videos

* ["Martin Fowler" scrum](https://www.youtube.com/edit?o=U&video_id=DeIhzvdGO28)
* [AV Marketing Meeting](https://www.youtube.com/edit?o=U&video_id=Lw79fDuia3Q)
* ["Kent Beck" scrum](https://www.youtube.com/edit?o=U&video_id=veCjZQEJLJk)
* [LocalSupport "Kick Off"](https://www.youtube.com/edit?o=U&video_id=h9d0_Cjen6o)
