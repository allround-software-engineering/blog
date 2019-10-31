---
layout: post
title:  "Personal Knowledge Base Overview"
date:   2019-10-18 22:45:54 -0700
categories: personal-knowledge-base
published: true
---

## Why

I believe we all have this moment: "What did I do about this last time?"

We have so many things going on at work, in life. It is easy to lose threads. We just need to note it down somewhere.

Another pain point I have it when I am writing emails/documentation to explain something, I had to constantly break my writing flow to look up something. For example, copy link to reference document, or go to a web page to get latest data. It would be nice to have a knowledge base to research these things for me first and fill in the blanks automatically.

## What

### Phase 1

I will create a command line tool for noting down things in a Git repo.

### Phase 2

I will create another tool or daemon service that will scan the notes and automatically organize the notes.

### Phase 3

The daemon will automatically fetch latest info and update existing knowledge base entries.

### Phase 4

The knowledge base will propose domain models (See Design/Domain Model) and allow uses to update domain models. The knowledge base will re-organize/search/present entries using these domain models.

## Design
### Architecture Diagram

![architecture diagram](/blog/graph/2019-10-18-personal-knowledge-base-1.png)


### Domain Model

There should be many models, each with different focus.

All models are wrong, some are useful. Therefore, we do not try to construct a complete and correct model.
