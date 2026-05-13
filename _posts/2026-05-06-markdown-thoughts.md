---
title: Your Lab Notebook Should Run on Markdown
date: 2026-05-13 02:00:00 -0600
categories: [Lab Update, Lab Notebook, Markdown]
tags: [update, markdown, obsidian, lab-notebook]
image:
  path: assets/images/obsidian_run.png
  alt: Ghost running through an Obsidian landscape. Courtesy Victoria R.
---

## Lab Notebooks as a Foundation of Progress
When we do something worth doing in science, it has to be properly recorded. Otherwise, it might as well have never happened. More explicitly, if we wish to make claims in scientific investigation, there must be evidence supporting or refuting some hypothesis. This means we need to know the "who", "what", "when", and "how" of any experiments or observations that compose our evidence.

Being generally aware of this, scientists record detailed notes, usually in the form of a lab notebook. If scientific knowledge is a tower, lab notebooks are the foundation, often invisible but completely essential for the structural integrity of progress.

## The Problem with Physical Lab Notebooks
When lab notebooks had to be physical books, there was not a lot of room for creativity in the format. Maybe there were different sizes or variable grid patterns. But the fundamental product was a bound volume that could be easily carried and filled with experimental records. Those who remained in a lab a long time filled bookshelves with multiple volumes of their lab notes. 

Relatedly, experimental protocols were often a page ripped out of one of these notebooks or a typed document that was shared and printed out. These often found their way into a 3-ring binder.

Of course, relying on preservation of a physical, singular artifact, like a bound lab notebook, for scientific knowledge is not ideal. If the notebook ever becomes lost or damaged, the information and knowledge contained therein is lost. People who need to view the experimental records must travel to the lab of origin. There are some workarounds for these vulnerabilities, like carbon copies, but these are limited and often not bothered with.

More speculatively, I worry that, with some exceptions, physical lab notebooks feel more like personal property of their author and are rarely viewed by supervisors. I worry that this does not encourage the establishment of scientific accountability (faithfully recording all the relevant experimental designs, events, and rationale), weakening science. In other words, there's an observability and accountability problem with physical lab notebooks.

## The Problem with Electronic Lab Notebooks
Scientists are using the computer for research more often, and most scientific instruments produce digital records like images or tabular data. Of course, some scientists exclusively use the computer for research and write scientific code, e.g. bioinformaticians (like me these days). Naturally, individuals and labs started transitioning to electronic lab notebooks (ELNs), which overcome some of the issues with physical lab notebooks and allow for faster composition/recording plus ease of copying/pasting, tabular formatting, and search. Of course, you could always print out protocols to bring to the bench for your experiments.

I remember that when I started graduate school in 2014, I did what I felt was most convenient at the time. I simply opened a Microsoft Word document each day, added the date, made a to-do list, then took semi-structured notes on what I did on the bench and I pasted any python code or terminal commands into the document. This became unruly and difficult to track projects. The searchability of a directory of hundreds of Word documents quickly deteriorated. 

So, I switched to Microsoft OneNote, and I'm told this remains a pretty popular choice these days. OneNote allows for hierarchical folder and note organization, much better searchability, automatic OneDrive backup, and freehand drawing. It even has note version history and read/write permissions, which, as a PI, I can now appreciate. 

Sensing an opportunity, a variety of companies have launched their own electronic lab notebook software as a service. These often look like the OneNote binder format with a smattering of extra science-oriented feature integrations like molecular cloning software and bioinformatics GUIs such as Geneious. They also tend to be convenient for real-time collaboration.

So, what's the problem?

One issue, shared almost universally amongst commercial ELNs is the problem of **vendor lock-in**. For example, if you move to a new institution or your institution changes supported ELN vendor (this is common in my experience), what are your options for migrating to a new system? I cannot speak for all vendors, and it's also possible some of my information is out of date, but typically, OneNote and commercial ELNS do not allow export of your notes to a convenient format. OneNote, for example, seems to allow note-by-note PDF export which is very tedious and destroys the functionality (e.g. search) and editability of notes, and some other vendors have XML format export which is not human-readable and requires specific software to read. 

Because of this, I don't believe these solutions are the right fit for preserving the scientific record. I think many of the features and integrations (like lab inventory or analytics) are simply to increase lock-in, dependency, and lab inertia for the product.

Other issues include challenging learning curves and cost (sometimes thousands of dollars per person per year). Cloud backup and syncing also causes more than a few headaches, especially as notebook size increases.

## Is Markdown-based Notetaking the Best Solution?
So, what do I do now and why do I think it's a better way?

The basic system is:
- Directory full of markdown (`.md`) files as individual notes.
- Daily driving in [Obsidian](https://obsidian.md/) for composition, production tools, and templates.
- Version control with git (GitHub in my case).
- Separate storage solution for large files (OneDrive).

[Here](https://github.com/tiszalab/obs_lab_notes_frame) is the publicly available framework for the Tisza Lab's notebook system. You can follow the instructions to get your own private notebook set up in about 15 minutes.

### So what does this solution provide?

**A simple, powerful, and near-universal file format**. What's cool about [markdown](https://www.markdownguide.org/basic-syntax/) is that it's extremely readable and composable in a plain-text renderer (like Notepad) and gains functionality through software like Obsidian, VS Code, or any of hundreds of other open source applications that render it. 

**Accessibility and functionality**. Lab notes are both a record and an organizational tool for scientists. What makes Obsidian feel so good are its "second brain" features, offered as standard and community plugins, that help ideas come to life and projects remain organized. Some favorites are:
- [tasks](https://github.com/obsidian-tasks-group/obsidian-tasks) (for planning and prioritizing)
- [dataview](https://github.com/blacksmithgu/obsidian-dataview) (for searching, parsing, and formatting related notes)
- [advanced tables](https://github.com/tgrosinger/advanced-tables-obsidian) (for making and displaying tables)
- [callouts](https://github.com/eth-p/obsidian-callout-manager) (for emphasizing parts of notes)
- [calendar](https://github.com/liamcain/obsidian-calendar-plugin)
- [charts](https://github.com/phibr0/obsidian-charts) (making nice graphs from your tables)
- [kanban](https://github.com/obsidian-community/obsidian-kanban) (project management)
- [excalidraw](https://github.com/zsviczian/obsidian-excalidraw-plugin) (sketch out systems or ideas)

Plus there are the wonderful built-in features like tag, template, note properties, link, and knowledge graph system. Oh, you can also use Obsidian on your phone!

**Beautiful Documents**. It's quite satisfying to compose a well-formatted [protocol](https://github.com/tiszalab/obs_lab_notes_frame/blob/main/protocols/Reverse%20Transcriptase%20and%20PCR%20-%20Tiled%20Amplicon.md), see your task list automatically populate, and edit a data table. To me, Obsidian-flavored markdown simultaneously provides a no-distraction notebook environment and a feature-rich toolset. 

**Version history and read/write permissions**. It's somewhat simple to make your notes a [git repo](https://git-scm.com/) that will enable you track when and how everything is created and modified plus who did it. Despite git's well-earned reputation for complexity, this is a pretty straightforward use-case. While git can be self-hosted on a NAS or HPC, the easiest (and free) way to do this is with [GitHub](https://github.com/) via [GitHub Desktop](https://desktop.github.com/download/). GitHub Desktop abstracts away much of the complexity here.

Labs can make a GitHub Organization where the PI can set read/write permissions for everyone's notebooks. It's quite convenient to be able to reference a lab member's notes at any time to see how data was analyzed, etc. To make git work, a scientist simply needs to "push" their lab notes to the remote server one or more times a day (there are even ways to automate this).

**Future proofing**. Even if the platform (e.g. Obsidian) goes away, all of the scientific records will still be interpretable by humans and renderable by other software. The git strategy means there will always be a safe backup of the notebook.

**No or low cost**. The basic layout I've described here costs me and my lab absolutely nothing. There are paid add-ons you might want like Obsidian Sync, or there may be costs associated self-hosting, but these tend to be quite minor.

### What limitations does this have?
There are a couple of notable limitations with this system, but I believe they're quite minor.

**No realtime collaboration**. With git, you cannot simultaneously edit a file on multiple computers and have those changes appear realtime. However, I've never in my 14 years of scientific experience wanted this feature for lab notes.

**Limited integration with analytics software**. If you need Geneious or Excel in the same pane as your notes, that requires complex files and render capability that Obsidian does not have. Maybe this will change in the future.

**Data storage stays separate**. Git is logistically limited by repo size. In my experience, anything over 100 MB starts to strain the software, and it's overall not meant for large datasets. Git large file storage (LFS) could get around this, but I haven't explored it. I find it more convenient to keep your lab notes in a separate bin from large datasets. Commercial data storage and retrieval services like OneDrive, Box, DropBox, etc, tend to be "good enough" for keeping data that only needs occasional access. All of these services have the ability to generate permalinks to stored files and directories that can and should be linked in lab notes.

### Thoughts on AI integrations
I'm still somewhat conflicted in use of AI/LLMs in scientific notekeeping. Their potential is obvious (LLMs can compose much more text much more quickly than humans therefore increase observability of experiments and decrease burden on researchers), but its downsides are real. If AI "hallucinates" numerical data, or makes a mistake, it lacks the accountability of a human scientist.

That said, current LLMs "love" markdown files and clever people could easily use these tools to improve the coherence of their knowledge base and expand their notebooks. AI makes it easy to make custom Obsidian stylings and will readily write personal plugins if so desired. I could also imagine a system where a scientist at the bench could "speak" with a model while pipeting to more easily record numbers and ad hoc modifications.

## This is Not a Post about LIMS or Compliance
Notably, large labs/centers that need a Laboratory Information Management System or have special compliance requirements are likely need something more complicated than the proposed markdown-based system.

## The Markdown Army is Always Recruiting
We have an obligation to record science faithfully and in real time, yet the ever-growing stack of work software often gets in the way. Using this markdown/Obsidian system truly makes my day-to-day and long-term scientific life a bit better. 

So, try the [framework](https://github.com/tiszalab/obs_lab_notes_frame), open an issue if you have questions, and let me know what you think on BlueSky (@miketisza.bsky.social).

