---
title: Your Daily Dose of AI Slopware
description: I built a job tracker instead of applying to jobs.
date: 2026-11-17
tags: [Projects, Job tracker, Claude Code]
draft: false
---

## Drafting

I am looking for a job. This is the part of the story where a sensible person applies to more of them.

I built a tracker. Then I rebuilt it. About 22 hours passed between the first line of code and the redesign going live,¹ and every one of those hours could have gone to job applications. Some of them probably should have.

*¹ Wall-clock hours. Sleep is in there. So is lunch. The agents did not take lunch.*

The internet has a word for software made fast, with AI, and without a plan worth the name. Slopware. I'm keeping it. This is slopware, and I use it every morning. It solves one problem, which is that I want to know where things stand and what happened while I was asleep. That problem is mine. The app is for me. You may look. There's a demo you can click around in at [labs.thezdev.com/job-tracker](https://labs.thezdev.com/job-tracker/).

Terms and conditions. I will not maintain this. I will not fix your bug. If you open an issue I will read it the way everyone reads terms and conditions. Every company in the screenshots is fictional, partly because my real search is nobody's business and partly because Blockchain for Dogs would be a lot to explain.

## Applied

Version one went live on a Monday night. Python, FastAPI, SQLite, a login page, a server I pay for. It already did the thing I wish recruiters did: Claude reads my email, notices when a rejection or an interview invite arrives, and updates the tracker without being asked twice.

Version one was also designed in a hurry by a language model I was rushing. The top of the page said the same five numbers three times. Cards, then a bar chart, then a row of filter buttons, each one announcing "Applied: 2" as if for the first time. The thing I actually needed, what's due today, sat in a box on the second row like a kid at the adults' table. Changing a status took five clicks and a pop-up.

On Tuesday I asked Claude to audit it like a principal product designer with a grudge. It obliged.

<figure class="shot tall">
  <a href="/images/slopware-job-tracker/before.webp"><img src="/images/slopware-job-tracker/before.webp" alt="The old tracker" width="1280" height="1606" loading="lazy" /></a>
  <figcaption>Exhibit A. Five numbers, three times. The useful part is on the right, trying not to make eye contact.</figcaption>
</figure>

## Recruiter screen

By Tuesday, the tracker part was done. It stored applications, kept a timeline, and Claude kept it current from my inbox. Functionally, a spreadsheet with ambition. Every job tracker on earth does that much, including the free ones and the one you made in Google Sheets in 2019.

What it didn't do was fit the way I actually use it. That's the part a user notices, so that's the part I cared about. The audit ended with three questions, and the answers were mine to give.

What do you want to know first when you open it? Where things stand. Then what changed since I last looked, because Claude edits this thing while I sleep and I want a diff. Desktop or phone? Desktop, most of the time, so design for the big screen and keep the phone usable. Colors? Keep them. Then let me change every one of them, and the font, and the spacing.

I kept making calls as it took shape. Themes should sync between my computers and leave my phone alone, because a phone is a different place to read things, even if I end up picking the same theme. Halfway through I added a flow chart with filters and an image download, because a picture of a pipeline does more in a conversation than a list does. Every screenshot came back to me, and plenty went back with a no. When it looked right, I said ship it.

For the record, and so nobody asks me to explain the CSS: I didn't write the code. I directed AI agents in Claude Code and they did the typing. A lead agent wrote the foundation and a spec. An advisor model read over its shoulder at the moments that mattered. Four builder agents worked at the same time in separate files: the list, the detail drawer, the theme editor and the flow chart. My job was the one I'd want on a real team. Know the user, decide what matters, cut what doesn't, sign off on the release. Conveniently, the user was me.

~~I managed a team of six.~~ Six language models put up with my product requirements for a day.

## Interviewing

The tour. Notice how little of it is new data. Same applications, same dates, same notes as version one. What changed is what you see first, how fast you can act on it, and how far you can bend it to your taste. That's the product.

### The first thing you see

A strip of stage counts. Under it, every live application grouped by stage, closest to an offer at the top, which is also the order of my anxiety. On the right is Today: only the things that need me, each with a button that makes the problem go away for now. Overdue gets Done or Snooze. Twenty quiet days gets Followed up or Ghosted. I suspect Ghosted will become the most-pressed button in the app.

<figure class="shot">
  <a href="/images/slopware-job-tracker/main-view.webp"><img src="/images/slopware-job-tracker/main-view.webp" alt="Main view with the Today column" width="1600" height="1000" loading="lazy" /></a>
  <figcaption>The main view. Vaporware Ventures said they'd circle back. They have not circled.</figcaption>
</figure>

### The overnight report

Claude updates this thing while I'm not looking, so the second panel is a diff of my life. "Since you last looked" lists every change I didn't make, signed by whoever made it. It doesn't clear itself when the page refreshes. It waits until I click Mark all seen, like a responsible adult opening their mail.

### Fewer clicks

Status changes happen on the row now. Click the badge, pick the stage, gone. Closing an application asks what you learned, a question I have come to resent. Everything else lives in a drawer that slides in from the side. Every field edits in place, and the resume I sent opens right there, so I can check what I claimed.

<figure class="shot">
  <a href="/images/slopware-job-tracker/status-menu.webp"><img src="/images/slopware-job-tracker/status-menu.webp" alt="Status menu on a row" width="1600" height="896" loading="lazy" /></a>
  <figcaption>Two clicks. It used to be five. I'm keeping the other three.</figcaption>
</figure>

<figure class="shot">
  <a href="/images/slopware-job-tracker/drawer.webp"><img src="/images/slopware-job-tracker/drawer.webp" alt="Detail drawer" width="1600" height="1000" loading="lazy" /></a>
  <figcaption>The drawer. Unicorn Stables Inc. has made an offer. The letter is in Comic Sans, which I'm treating as a negotiating position.</figcaption>
</figure>

The archive is where applications go to become anecdotes. Every closed one keeps a one-line lesson, and the lessons are the best writing in the app.

<figure class="shot">
  <a href="/images/slopware-job-tracker/archive.webp"><img src="/images/slopware-job-tracker/archive.webp" alt="Archive with lessons learned" width="1600" height="1000" loading="lazy" /></a>
  <figcaption>All fictional. Any resemblance to real hiring processes is the point.</figcaption>
</figure>

### A Sankey diagram, because I could

Halfway through the build I asked for a Sankey chart. Nobody needs a Sankey chart of their job search. It shows how applications moved through the stages and where each one ended up, which makes it mostly a diagram of the word no. It filters by date and source and downloads as an image, in case a relative asks how the search is going and I need the conversation to end.

The agents were weirdly principled about it. They refused to draw a stage that wasn't recorded. Skip the recruiter screen and your line skips that column. Old applications that arrived with only an outcome go through a dashed box labeled Stage not recorded, the most honest thing a chart has ever said to me.

<figure class="shot">
  <a href="/images/slopware-job-tracker/flow-chart.webp"><img src="/images/slopware-job-tracker/flow-chart.webp" alt="Flow chart dialog" width="1600" height="1000" loading="lazy" /></a>
  <figcaption>The flow chart. Read left to right, like a tragedy.</figcaption>
</figure>

<figure class="shot">
  <a href="/images/slopware-job-tracker/flow-export.webp"><img src="/images/slopware-job-tracker/flow-export.webp" alt="Exported flow chart" width="1600" height="993" loading="lazy" /></a>
  <figcaption>The export. Suitable for framing, or for a slide titled Learnings.</figcaption>
</figure>

### The theme editor got out of hand

I asked to keep the colors and also be able to change all of them, and nobody stopped me. There are five themes and an editor for every color in light and dark, plus font, size, spacing, corner roundness and badge style. Pick colors that make the text unreadable and it says so, politely, with a contrast ratio.

Themes sync across devices: one for my computers, a separate one for my phone. My desktop and laptop agree on everything. My phone does what it wants.

<figure class="shot">
  <a href="/images/slopware-job-tracker/theme-paper.webp"><img src="/images/slopware-job-tracker/theme-paper.webp" alt="Appearance panel, Paper theme" width="1600" height="1000" loading="lazy" /></a>
  <figcaption>Paper. A serif font on cream, for job hunting with a fountain pen.</figcaption>
</figure>

<figure class="shot">
  <a href="/images/slopware-job-tracker/theme-dark.webp"><img src="/images/slopware-job-tracker/theme-dark.webp" alt="Dark mode, Stage hues theme" width="1600" height="1000" loading="lazy" /></a>
  <figcaption>Dark mode, Stage hues. For applying to jobs at 1 a.m.</figcaption>
</figure>

### For the keyboard people

j and k move. s changes status. n is new. f opens the flow chart, for when you need to feel something. ? shows the rest. The phone version puts the list first and doesn't try to be clever.

<figure class="shot">
  <a href="/images/slopware-job-tracker/shortcuts.webp"><img src="/images/slopware-job-tracker/shortcuts.webp" alt="Keyboard shortcuts help" width="1600" height="1000" loading="lazy" /></a>
  <figcaption>Every shortcut on one card.</figcaption>
</figure>

<figure class="shot phone">
  <a href="/images/slopware-job-tracker/phone.webp"><img src="/images/slopware-job-tracker/phone.webp" alt="Phone view" width="1170" height="1992" loading="lazy" /></a>
  <figcaption>The phone. Fewer features, same outcomes.</figcaption>
</figure>

## Offer

What 22 hours bought, in things a computer can count.

<table class="facts">
  <tbody>
    <tr><td>First commit</td><td>Monday, Nov 16, 9:12 PM</td></tr>
    <tr><td>Redesign live</td><td>Tuesday, Nov 17, 7:07 PM</td></tr>
    <tr><td>Commits on main</td><td>10</td></tr>
    <tr><td>Automated tests</td><td>50</td></tr>
    <tr><td>Front-end code</td><td>about 4,900 lines, no framework, no build step</td></tr>
    <tr><td>Back-end code</td><td>about 870 lines of Python</td></tr>
    <tr><td>AI agents directed</td><td>6</td></tr>
    <tr><td>Who decided what it should do</td><td>me</td></tr>
    <tr><td>Code typed by me personally</td><td>see Recruiter screen</td></tr>
    <tr><td>Job offers generated by the app</td><td>0</td></tr>
  </tbody>
</table>

I did not negotiate.

## Rejected

Some things did not go to plan.

My real flow chart is a gray river. All ten of my closed applications came from an old import that kept only the outcome, so the chart routes every one of them through Stage not recorded and out into Rejected, Withdrawn and Ghosted. As a picture of a job search it is hard to argue with. It fills in as I record stages from here on.

The drawer has boundaries. Try to close it with unsaved changes and it won't. Try to click away and it won't. It offers to discard your edits and then it waits, arms folded. My own test script sat there for thirty seconds and timed out, which I found validating.

A badge style called Solid put white text on pale blue and was unreadable in some themes. It's called Strong now, with dark text. I'd hire Strong.

On the way out the door, the advisor caught a caching bug that would have broken the page for anyone who had it open during the deploy. That was going to be me.

A hook in my setup nagged me to commit my work every single time I stopped. It was right every single time, which is the most annoying thing a hook can be.

## Ghosted

This is where a post like this lists five lessons and asks whether you agree.

No.

Fine, one. Storing a list of jobs is solved. A spreadsheet does it. The reason I open this one every morning is the presentation: what sits on top, what's one click away, what color it is at 1 a.m. Deciding that was the hard part. The code was the easy part, and I didn't even do that.

This is also where I'd promise to keep it up to date. The code is at [github.com/mnmilford/job-tracker](https://github.com/mnmilford/job-tracker). Take it. Change it. Don't tell me. If you want your own copy, the README walks you through it, from a two-minute demo on your laptop to a real install on your own server.

To be continued.
