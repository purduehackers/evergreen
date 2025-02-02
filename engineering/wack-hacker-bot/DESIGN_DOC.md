# Wack Hacker Design Doc

- **DRI**: [@rayhanadev](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/rayhanadev.md)

## Objective

Wack Hacker is meant to provide access to multiple utilties and tools that are useful
for organizers and community members via Discord commands and interactions.

## Background

### Problem

Wack Hacker was created because we used to use a Discord bot called @nightcrawler for
everything related to Purdue Hackers, however I didn't have easy access to the codebase
nor the Discord bot itself, so I created a new bot to develop on.

### Stakeholders

- Organizers
- Community Members

### Existing Solutions

Nightcrawler is the existing solution, but it is not maintained and I don't have access
to the codebase.

### Alternative Solutions

1. Bother Matthew and Hazel to give me access to the codebase and the bot

## Requirements

### Goals

- Provide access to multiple utilities and tools that are useful for organizers and community members
- Open source and make the deployment process easy for future maintainers

### Non-Goals

- Replace Nightcrawler
- Interact with the community (a lá Bobert)

### Constraints

- Must be a Discord bot
- Must be open source
- Must be easy to deploy
- Must be easy to maintain

## Design

### Architecture

- **Language**: TypeScript (Bun)
- **Dependencies**: `discord.js`

### Implementation

Wack Hacker is a Discord bot that is written in Typescript and Bun and uses the Discord.js
v14 library. It will likely hook into external APIs such as OpenAI and Groq for certain
AI features.

It will likely use a database, Fly.io has a Tigris KV store that I could use.

There are no specific commands planned, but rather it will be designed to be extensible
and easy to add new commands to.

### Deployment

It will be hosted on Fly.io, and will be deployed via GitHub Actions.

### Testing

I could write unit tests for each of the functions that the bot will have, but I don't
think it's necessary. Likely will test implementation by running the bot in a test server.

## Milestones

- Start Date: December 21st, 2024

## Additional Considerations

### Security

Any commands that are for organizers only (concerning PII) will be locked behind a
permission check.

### Performance

Not a concern for this project.

### Maintenance

The Discord bot will be deployed to GitHub and maintained by the DRI. It will be run during
Prep prior to the ceremony, and if there are any issues, the DRI will be responsible for fixing them.

## References

> Optional. Links to any external resources that are relevant to the project.
