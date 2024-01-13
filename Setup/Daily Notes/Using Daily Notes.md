---
tags:
  - guide/daily-notes
---
## Setup
* Enable the Daily notes Core plugin.

![[Screenshot 2024-01-09 at 16.12.09.png]]

* Create a directory `Daily Notes` in which the notes will be stored.
* Create a directory for templates `Templates/Daily Notes` and create a new note template. See further below for my current template I use.
* Setup the plugin to create the daily notes in the `Daily Notes` directory and specify the template file to use.

![[Screenshot 2024-01-09 at 16.18.37.png]]

* I prefer to store my notes using the format `YYYY/MM-MMMM/YYYY-MM-DD` which will result in a folder hierarchy like the following screenshot.

![[Screenshot 2024-01-09 at 16.18.58.png]]

* To create a new daily note, you can use the command palette `Cmd + p` and search for "Daily notes: Open today's daily note". You can also create a new note from the Calendar view (Calendar community plugin).

![[Screenshot 2024-01-09 at 16.19.12.png]]
## Template

This is the template I currently use for my daily notes.

* I like to use the popular [Templater](obsidian://show-plugin?id=templater-obsidian) plugin to do some automatic fill in of values. [[Templater settings]]
* Markdown

```
---
date: <% tp.file.creation_date() %>
tags:
  - daily
---

# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>

## I am grateful for

1. <% tp.file.cursor() %>
2. ~
3. ~

## What would make today great?

1. ~
2. ~
3. ~

## What is the one thing I can do today to move my goals forward?

1. ~

---

## Highlights of the day

1. ~
2. ~
3. ~

## What did I learn today?

* ~
```
  
* Source view

![[Screenshot 2024-01-13 at 12.18.36.png]]
* Example of when a new note is created. The date and time is automatically filled in and the cursor is placed ready for me to start filling in the first thing I am grateful for in that moment.
![[Screenshot 2024-01-13 at 12.14.39.png]]