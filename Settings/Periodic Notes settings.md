---
tags:
  - settings/periodic-notes
---

## Weekly Notes

* First create a template that will be used for new weekly notes. See my template source further down below.
* Turn on weekly notes and give it the template to use.
* The file format I use is: `YYYY/MM-MMMM/[W]-ww` and the notes are stored inside my `Daily Notes` folder.

![[Screenshot 2024-01-14 at 18.07.14.png]]

## Monthly Notes

* Create a template for monthly notes. See my template source further down below.
* Turn on monthly notes and give it the template to use.
* The file format I use is: `YYYY/MM-MMMM` and the notes are stored inside my `Daily Notes` folder.
![[Screenshot 2024-01-14 at 18.19.30.png]]
## Current templates I use

### Weekly

```
---
date: <% tp.file.creation_date() %>
tags:
  - weekly
---
# Week  <% moment(tp.date.now()).startOf("week").format("WW: MMMM Do") %> - <% moment(tp.date.now()).endOf("week").format("Do YYYY") %> 

## What went right this week?

1. <% tp.file.cursor() %>
2. ~
3. ~

## What went wrong this week?

1. ~
2. ~
3. ~

## What is the one thing I can do next week to move my goals forward?

1. ~

```

### Monthly

```
---
date: <% tp.file.creation_date() %>
tags:
  - monthly
---
# <% moment(tp.date.now()).format("MMMM YYYY") %>

## What went right this month?

1. <% tp.file.cursor() %>
2. ~
3. ~

## What went wrong this month?

1. ~
2. ~
3. ~

## What is the one thing I can do next month to move my goals forward?

1. ~

```
