# State of Evergreen 05-30-2025, according to matthew

Evergreen was first proposed in [Galactic Empire](https://blog.purduehackers.com/posts/galactic-empire) as a recurring creative initiative for documentation. Its stated goals were:

- Document the values and practices of Purdue Hackers so that knowledge is preserved; everything from high-level goals to specific event retros and micro-lessons
- Reduce the activation energy required to write documentation
- Make documentation an ongoing part of everything we do in Purdue Hackers, not something reserved for after the fact
- Give community members ownership by encouraging them to contribute to the project
- Help club leaders at other schools learn from our successes and failures, in addition to future Purdue Hackers

I think we are not currently on track to realize this vision. A year ago, I imagined that today we’d have write-ups on all of our 2024-25 events, RFCs for creative projects and high-level org direction contributed to by community members, technical guides, and lots of opinion docs; today, we have a few RFCs (e.g. “a hack night where people actually make things”), write-ups (kiln retro), and technical guides (hack night badges), but nothing like the comprehensive documentation I was hoping for.

## Problems with Evergreen

Here are a few things that are currently going wrong in my opinion:

- **GitHub is the wrong format for Evergreen.** A year ago I thought it was actually the perfect format because we had built-in version control and pull requests were a natural way for people to propose changes, but in reality it adds way too much friction to check out a branch, find the right folder, follow the style guide, and then wait for Ray or me to merge it, especially if blocking changes are suggested.
- **We have been doing way too much premature optimization.** We have spent more time on organization and formatting than we have on actually writing documents, and this has often stopped documents from being written. The Evergreen style guide, as implemented, has resulted in some documents being stuck in review hell and never merged because of inconsequential style & formatting nitpicks. Lots of early documents were also _removed_ for these reasons and new versions have yet to be written. Writing a new document feels daunting because we have to be sensitive of which folder we’re writing in, the style guide preferences (e.g. “no attributions”, linking to documents), and not including PII, not just before “publishing” but before first pushing changes to a branch, since it’s an open source repo.
- **It’s hard to find things.** Despite only having a few documents on Evergreen, things feel deeply nested inside folders and subfolders and it’s difficult & frustrating to find documents that I know exist. This is compounded by so many early documents having been deleted, so even if I remember a document existing it might turn out to be in the Git history of a branch somewhere. This also makes it harder to write documents because I want to be able to reference other documents, but I can’t do that easily because I have to switch contexts, open the Evergreen GitHub repo, find the document, and copy the URL from my URL bar. And if we ever change the title of the document or move it to a different folder (which is common while it’s still early), the link will silently break.
- **We’ve been bikeshedding.** Evergreen has been the source of many hours-long bikeshedding conversations in Discord this spring which has made it feel draining to think about. Many individual documents have also been the source of bikshedding that led to them not being merged, e.g. the kiln retro.
- **We haven’t figured out how to manage ownership for contributions.** An early problem was that we wanted to ideally backfill knowledge from before we started Evergreen but that many of us knew, e.g. design docs for engineering projects like the door opener. We tried assigning these backfilled documents as tasks, but people did not respond well to this because it felt unnecessary (and this feeling is valid; documentation never feels urgent, even if it is necessary, which is why so many orgs struggle with it). So we refocused Evergreen to be strictly an ongoing best-effort basis, but that means it was nobody’s job so lots of documents didn’t get written (this was compounded by it being too high-friction to start a new document).

If I had to summarize the problems with Evergreen in one sentence, it would be that contributing to it is too high-friction right now.

## My proposal for improving Evergreen

The guiding principle behind Evergreen should be that **having a document is better than not having a document.** Right now, while Evergreen is still sparsely-populated, we should prioritize adding documents by any means necessary, and fix the problems that arise from this as they arise.

Some actionable proposals:

### Move off of GitHub and to something closer to a CMS or a wiki.

This should have 3 requirements:

1. It should be very easy to add or edit documents — no pull requests, no local checkout, just markdown in an editor that launches and performs fast.
2. A way to publish publicly but not have the process of writing be public. This way we don’t have to worry about things like PII while we’re in the process of writing a document, which breaks flow.
3. An easy way to link between documents, ideally within the editor itself (AKA no diving through the archives in a separate tab and copy/pasting a URL into Markdown). These links should also persist even if the location of the document changes.

I propose self-hosted Obsidian because it checks all these boxes, but I’m sure some other wiki software does too. We should also consider other digital-garden software like Quartz.

I was hesitant to propose this before because I really like that GitHub is built around commits, which I think are important to show for living documents like the ones we have in Evergreen. But I don’t think its downsides are worth it and don’t want to over-index on version history. We can make our own solution to this in Obsidian/Quartz/etc if we care so much.

### Write everything from individual perspectives by default.

One of the reasons the Kiln retro sparked so much bikshedding was because it was written from the perspective of one person, but Evergreen documents currently imply that they represent the collective opinion of Purdue Hackers, and other people took issue with some of the opinions and presentation.

I think a better way to do this is for Evergreen documents to contain attributions for the primary author(s) and imply that the contents represent their personal views. If a document is intended to represent Purdue Hackers (e.g. team structure documentation), then that should be explicitly mentioned. It should be okay to have multiple documents about the same thing written from two different perspectives, especially for things like event retros.

A risk this introduces is that it makes it harder to learn useful things from Evergreen documents since some documents may contain conflicting opinions and not contain a clear narrative. But I think this only applies to things like event retros and I’m not convinced it’s actually as big of a problem as it sounds. Even if it’s not perfect, I think enforcing a single narrative actually ends up just publishing the opinions of one person and/or enables bikeshedding & adds more friction to writing the most important documents. A document is better than no document.

### Use a style guide, but make it a suggestion instead of a hard requirement

A style guide is a great way to help with the blank-page problem by giving people a prompt or a piece of a picture of a document, but rigorously enforcing top-tier standards prevents documents from being written and makes time be spent on nitpicky changes instead of writing.

The reason we were so strict on style guides in the first place is because having no standard for structure can result in useful information being hard to find or presented in unclear ways. But evidently we are already facing this problem for the documents that managed to get through the arduous style guide review process. It’s okay for documents to feel a little bit inconsistent at first and then standardize later on a few necessary requirements *as needed*. A document is better than no document, so let’s remove all the friction we can.

#### Corollary: Embrace attributions

This is implied in the above point, but it should be mentioned explicitly: our current style guide discourages attributions, but I think this is wrong because under the current style guide I would never write a document like I am now, which is haphazardly-written before a flight and deeply carries my own voice. This document was obviously written by me and if I had to pretend to speak on behalf of Purdue Hackers I would have stripped a lot of what I’ve written. This document being truly my own also makes me feel more ownership over the Evergreen project since I’m contributing My Piece to it, which makes me more invested in this piece & its greater whole.

The Kiln retro that [idk if i can say this person’s name in a public github repo because of pii things and idr how to link to their dark-forest thing so i’m not bothering] wrote should be attributed to them and belong to them; it should be their piece of the Evergreen project, which inspires other pieces.

### Build systems to fix problems as needed

Problems like the one of search can be solved with good digital-garden software and, TBH, LLMs & semantic search. We had the right instincts with bots like wack hacker / “evergreen it”. We can use Evergreen as an excuse to build cool software to automate and fix things, and we can also change the way we structure the project in the future to fix future problems in non-technical ways.

### Make everyone want to write documents, but don’t assign them as tasks

Documentation by nature feels arduous and unnecessary, so writing a document should not feel like a necessary Task. This may mean some documents won’t get written (e.g. backfilling things that happened in the past), but they weren’t getting written even when we did try to assign them as tasks, and doing so only turns Evergreen into a burden that assignees don’t want to think about, which can prevent them from writing documents in the future even if they do feel inspired.

We’ve seen that the people who care most about Purdue Hackers really want to contribute to the Evergreen project, but right now most of their potential contributions have not happened because it has been too high-friction to contribute to the project. If we reduce the friction to near-zero, what I think will happen is that the most dedicated people will start contributing much more, begin a positive feedback loop for themselves and more of the most dedicated people, and inspire less dedicated people to contribute as well (and perhaps turn them into more dedicated people).

---

I’m writing this before heading to the airport so it’s a little haphazard and I probably forgot to mention some things that I wanted to say. It’s also a little too long, but if I had more time I would have written a shorter letter. Hopefully this is still a good starting point for how to improve the Evergreen project, which I still believe is a necessary piece for maintaining Purdue Hackers long into the future.