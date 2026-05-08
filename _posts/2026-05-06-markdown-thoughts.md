---
title: The Markdown Army Needs your Lab Notebooks
date: 2026-05-07 02:00:00 -0600
categories: [Lab Update]
tags: [update, markdown]
image:
  path: assets/images/ghostvir.png
  alt: May 2026
---

# The Problem with Physical Lab Notebooks
When lab notebooks had to be physical books, there was not a lot of room for creativity in the format. Maybe there were different sizes or variable grid patterns. But the fundamental product was a bound volume that could be easily carried and filled with experimental records. For those who remained in a lab a long time, bookshelves were filled with various volumes of their lab notes. 

Relatedly, experimental protocols were often a page ripped out of one of these notebooks or a typed document that was shared and printed out. These often found their way into a 3-ring binder.

Of course, relying on preservation of a physical, singular artifact, like a bound lab notebook, for scientific knowledge is not ideal. If the notebook ever becomes lost or damaged, the information and knowledge contained therein is lost. People who with to view the experimental records must travel to the lab of origin. There are some workarounds for these vulnerabilities, like carbon copies, but these are limited and often not bothered with.

More speculatively, I think that the fact that, with some exceptions, physical lab notebooks feel more like personal property of their author and are rarely viewed by supervisors. I worry that this does not encourage the establishment of scientific accountability (faithfully recording all the revelant experimental designs, events, and rationale), weakening science. In other words, there's an observability problem with physical lab notebooks.

# The Problem with Electronic Lab Notebooks
Scientists are using the computer for research more often, and most scientific instruments produce digital records like images or tabular data. Of course, many scientists exclusively use the computer for research and write scientific code, e.g. bioinformaticians. This accurately describes me these days. Naturally, individuals and labs started transitioning to electronic lab notebooks (ELNs), which overcome some of the issues with physical lab notebooks and allow for faster composition/recording plus ease of copy/pasting, tabular formatting, and search. Of course, you could always print out protocols to bring to the bench for your experiments.

I remember that when I started graduate school in 2014, I did what I felt was most convenient at the time. I simply opened a Microsoft Word document each day, added the date, made a to-do list, then took semi-structured notes on what I did on the bench and I pasted any python code or terminal commands into the document. This became unruly and difficult to track projects. The searchability of a directory of hundreds of Word documents quickly deteriorated. 

So, I switched to Microsoft OneNote, and I'm told this remains a pretty popular choice these days. OneNote allows for hierarchical folder and note organization, much better searchability, automatic OneDrive backup, and freehand drawing. It even has note version history and read/write permissions, which, as a PI, I can now appreciate. 

Sensing an opportunity, a variety of companies have launched their own electronic lab notebook software as a service. These often look like the OneNote binder format with a smattering of extra science-oriented feature integrations like cloning and bioinforatics GUIs such as Geneious. They also tend to be convenient for real-time collaboration.

So, what's the problem?

One issue, shared almost universally amongst commercial ELNs is the problem of **vendor lock-in**. For example, if you move to a new institution or your institution changes supported ELN vendor (this is common in my experience), what are your options for migrating to a new system? I cannot speak for all vendors, and it's also possible some of my information is out of date, but typically, OneNote and commercial ELNS do not allow export of your notes to a convenient format. OneNote seems to allow note-by-note PDF export which is very tedious and destroys the functionality (e.g. search) and editability of notes, and some other vendors have XML format export which is not human-readable and requires specific software to read. Because of this, I don't believe these solutions are the right fit for preserving the scientific record. I think many of the features and integrations (like lab inventory or analytics) are simply to increase lock-in, dependency, and lab inertia for the product.

Other issues include challenging learning curves and cost (sometimes thousands of dollars per person per year). Cloud backup and syncing also causes more than a few headaches, especially as notebook size increases.

# Is Markdown-based Notetaking the Best Solution?
So, what do I do now and why do I think it's a better way?

The shortest answer is:
- Directory full of markdown (`.md`) files as individual notes.
- Daily driving in [Obsidian](https://obsidian.md/) for composition, production tools, and templates.
- Version control with git (GitHub in my case).
- Separate storage solution for large files (OneDrive).

### So what does this solution provide?

**A simple, powerful, and near-universal file format**. What's cool about [markdown](https://www.markdownguide.org/basic-syntax/) is that it's extremely readable and composable in a plain-text renderer (like notepad) as gains functionality through software like Obsidian, VS Code, or any of hundreds of other open source applications that read it. 

**Accessibility and functionality**. Lab notes are both a record and an organizational tool for scientists. What makes Obsidian feel so good are its "second brain" features, offered as standard and community plugins, that help ideas come to life and projects remain organized. Some favorites are tasks (for planning and prioritizing), dataview (for searching, parsing, and formatting related notes), advanced tables (for making and displaying tables), callouts (for emphasizing parts of notes), calendar, daily note (for a convenient note for daily tasks), Charts (making nice graphs from your tables), Kanban (project management), excalidraw (sketch out systems or ideas). Plus there's the wonderful built-in tag, note properties, link, and knowledge graph system. Oh, you can also use Obsidian on your phone!

**Version history and read/write permissions**. It's wonderfully simple to make your notes a [git repo](https://git-scm.com/) that will enable you track when and how everything is created and modified plus who did it. While git can be self-hosted on a NAS or HPC, the easiest (and free) way to do this is with [GitHub](https://github.com/) via [GitHub Desktop](https://desktop.github.com/download/). Labs can make a GitHub Organization where the PI can set read/write permissions for everyone's notebooks. It's quite convenient to be able to reference a lab member's notes at any time to see how data was analyzed, etc. To make git work, a scientist simply neeeds to "push" their lab notes to the remote server one or more times a day (there are even ways to automate this).

**Future proofing**. Even if the platform (e.g. Obsidian) goes away, all of the scientific records will still be interperable by humans and renderable by other software. The git strategy means there will always be a safe backup of the notebook.

**No or low cost**. The basic layout I've described here costs me and my lab absolutely nothing. There are paid add-ons you might want like Obsidian Sync, or there may be costs associated self-hosting, but these tend to be quite minor.

### What limitations does this have?
There are a couple of notable limitations with this system, but I believe they're quite minor.

**No realtime collaboration**. With git, you cannot simultaneously edits a file on multiple computers and have those changes appear realtime. However, I've never in my 14 years of scientific experience wanted this feature for lab notes.

**Limited integration with analytics software**. If you need Geneious or Excel in the same pane as your notes, that requires complex files and render capability that Osidian does not have. Maybe this will change in the future.

**Data storage stays separate**. git is logistically limited by repo size. In my experience, anything over 100 MB starts to strain the software, and it's overall not mean for large datasets. Git large file storage (LFS) could get around this, but I haven't explored it. I find it more convenient to keep your lab notes and large datasets in separate bins with separate strategies. Commerical data storage and retrieval services like OneDrive, Box, DropBox, etc, tend to be "good enough" for keeping data that only needs occassional access. All of these services have the ability to generate permalinks to stored files and directories that can and should be linked in lab notes.

### Thoughts on AI integrations
I'm still somewhat conflicted in use of AI/LLMs in scientific notekeeping. Its potential is obvious (it can compose much more text much quicker therefore increase observability of experiments), but its downsides are real. If AI "hallucinates" numerical data, or makes a mistake, it lacks the accountability of a human.

That said, current LLMs "love" markdown files and clever people could easily use these tools to improve the coherence of their knowledge base and expand their notebooks. AI makes it easy to make custom Obsidian stylings and will readily write personal plugins if so desired. I could also imagine a system where a scientist at the bench could "speak" with a model while pipeting to more easily record numbers and ad hoc modifications.

# This is Not a Post about LIMS or Compliance
Quickly, large labs/centers that need a Laboratory Information Management System or have spe