# Boat Design Doc

- **DRI**: [Ray](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/rayhanadev.md)

## Objective

Boat is a custom-built solution to our documentation problem – composing itself of a collection manager, access control management, a paned editor, and documentation web host.

## Background

### Problem

Evergreen is currently composed of two Github repos, [purduehackers/evergreen](https://github.com/purduehackers/evergreen) and [purduehackers/dark-forest](https://github.com/purduehackers/dark-forest). There have been many issues with this setup that were laid out [here](https://github.com/purduehackers/evergreen/blob/main/meta/retros/path-forward-05-30-2025.md). I would like to build us a custom-fit documentation solution that integrates into our existing workflows well and gives us great extensibility into the platform.

### Stakeholders

- Organizers

### Existing Solutions

- Github is an existing solution, but as mentioned above it has issues and causes high friction.

### Alternative Solutions

1. HedgeDoc: we currently use HedgeDoc and some of the good things about it include instant note creation and collaborative editing, but it lacks a great way to store and organize notes, only allows editing a single note at once, and doesn't have good ACLs. To share a note you need to make it public. Our current workflow involves taking notes in HedgeDoc, and then putting them in Evergreen, ultimately ending us back on Github to host Evergreen.
2. Quartz + Obsidian/Alternate Editors: This solution offers an improved editing experience to Github, but Quartz is ultimately powered by Github as a CMS, posing the same problems as we currently have. Quartz also lacks collaborative editing and instant note creation.
3. MediaWiki: MediaWiki is a full-fledged wiki software. It has decent organization of notes, ACLs, and search-ability. The platform itself, however, is dogshit. The Wiki editor has a learning curve, introduces unnecessary friction to contribute, and is not easy to use on mobile. Talk pages are Wiki's solution to meta-discussion, but most of our meta-discussion happens on Discord, and separating this doesn't feel effective to facilitating communication. It also isn't the most usable software, browsing is hard and unintuitive for those who aren't well acquainted with the Wiki, has a very bad UI/UX that's hard to build on, and is constrained W.R.T. formatting. My critiques on the usability can continue on to form a long list, but ultimately the differentiation comes down to Evergreen being fit to Wiki or us building a platform to facilitate Evergreen as effectively as possible.

## Requirements

### Goals

- Must be able to easily create notes
- Must have authentication to view and edit notes
- Must be able to easily edit notes (zero friction to open, make changes, and view)
	- Must be able to edit multiple notes in one view (projects)
	- Must be able to collaboratively 
- Must be able to easily access/view notes (outside editor)
- Must be able to define access controls for viewing and editing notes (share links)
- Must be able to easily search notes (knowledgebase search)

### Non-Goals

- Be a project management platform
- Allow users to edit content other than Markdown
	- Exception: I want to have Excalidraw integrated into the editor for quick sketches/drawings

### Constraints

- Must be a web interface
- Must be mobile friendly
- Must be low-friction in all processes (create notes, edit notes, leave feedback, deploy)
- Must be easily browsable

## Design

### Architecture

- **Language**: TypeScript (Bun)
- **Dependencies**: `next.js`, `codemirror`, `postgres`

### Implementation

I think the primarily inspiration for this platform will be web IDEs like Replit and Glitch, which offer zero-friction ways to edit files and deploy code. In this case, it will be editing Markdown in a WYSIWYG format and deploying a static site compiling the Markdown. They also have great models for managing collections (eq. projects), access control and generally indexing content for search.

The frontend will be implemented in Next.js. Authentication can be done through `next-auth`, integrating into whatever auth system we choose (Passports, Github, etc.). Data for collections/deployments/etc. will be stored in a Postgres database (`drizzle-orm` for ORM of choice). Uploaded assets can be stored in an S3 database (Vercel Blob, Minio for self-hosting) or something similar.

The backend will be a `elysia` server (Bun runtime) that implements operational transforms (OTs) so that edits can be easily stored and rolled back. OTs is the default change stack that CodeMirror uses and is easier to implement than CRDTs. I'm also not optimizing the editor for offline-first use-cases... idk could be something we want to see?

### Deployment

It will likely be hosted on Vulcan.

### Testing

N/A

## Milestones

- Start Date: June 16th, 2025
- Auth + DB Structure: June 18th, 2025
- Dashboard + Collection Management: June 20th, 2025
- CodeMirror Implementation: June 25th, 2025
- WebRTC Collaboration Server: June 29th, 2025
- File Structuring: July 1st, 2025
- Document Web Hosting: July 5rd, 2025
- Access Controls: July 7th, 2025
- Document Indexing + Search: July 10th, 2025

## Additional Considerations

### Security

ACLs can be a mix of Github and Google Docs. 

Roles:
- Admin: can manage all aspects of a collection
- Maintainer: can manage permissions and content in collection
- Editor: can create/edit content in collection
- Guest: can temporarily edit a certain files in a collection
- Viewer: can view content (readonly)

Have share links to allow for sharing collections/content (a lá Google Docs).

Collections can either be published (readonly), public (editable), internal, or fully private. Depending on the content one can choose the appropriate view level.

Content in collections can be drafted (omitted from published site), published (published in public site), or internal/hidden (only authorized users can view, omitted from published site).

Use `@` to mention members and easily search for users.

### Performance

Not a concern for this project.
### Maintenance

Maintained by DRI. Open source for contributions and future maintenance.

## References

> Optional. Links to any external resources that are relevant to the project.

- [HedgeDoc](https://github.com/hedgedoc/hedgedoc) - Editor implementation
- [Replit](https://replit.com) - Editor UI inspiration
	- https://blog.replit.com/code-editors
	- https://blog.replit.com/filetree-updates
	- https://blog.replit.com/the-journey-to-code-search
	- https://blog.replit.com/filetree
	- https://blog.replit.com/history2-release
	- https://blog.replit.com/leaky-uis
	- https://blog.replit.com/codemirror-mobile
	- https://blog.replit.com/threads-v2
	- https://blog.replit.com/splits
- [Obsidian](https://obsidian.md/)
- [iA Writer](https://ia.net/writer)
