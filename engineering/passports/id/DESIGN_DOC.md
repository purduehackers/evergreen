# ID Design Doc

- **DRI**: [Jack](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/imthesquid.md)

## Objective

Creating a universal authentication system for Purdue Hackers.

## Background

### Problem

Many Purdue Hackers projects necessitate keeping track of people’s identities (e.g. passports) or signing into an interface (e.g. issuing office). Instead of using external services Purdue Hackers should use their own internal system based around passports and make it available to anyone who wants to use it.

### Stakeholders

Anyone with a passport and all Purdue Hackers projects that require signing in.

### Existing Solutions

- Using other auth providers (Google, Github)

### Alternative Solutions

- Using other auth providers

## Requirements

### Goals

- OAuth compatibility
	- Usable with popular JS auth libs
	- Easy to implement
- Uses passports in a fun and interesting way
- Usable in a secure manner when necessary
- Store passport data and manage which one is active for each user

### Non-Goals

- Be cryptographically secure with just passports (out of scope, complicated, and expensive)
- Be the central hub for data storage with regards to each Hack Night attendee.

### Constraints

- Must work with all major platforms (i.e. no mobile apps)
- Must follow the entire OAuth spec as close as possible

## Design

### Architecture & Implementation

The server will run [Oxide Auth](https://github.com/HeroicKatora/oxide-auth), an OAuth server written in Rust. It will interact with our main database and manage all authentication requests.

### Data Model

Each user can have an arbitrary number of passports associated with them but only one can be active at any given time. Passports are registered through Passport Ceremonies.

### User Interface

A basic interface reminiscent of other current sign in platforms will ask the user if they want to approve the connection with the target app and list the scopes the app is requesting after they verify ownership of their passport. Passport ownership is verified by entering the passport number then scanning the passport with a phone to contact the server and allow the sign in.

### Deployment

Users can integrate with ID using the example repo as a base.

## Milestones

- Full OAuth support within a month
- Easy integration instructions/example within a week afterwards

## Additional Considerations

### Security

Passports are not secure since they just use basic NFC tags. For most things this is fine but for high-security apps it is possible to swipe an administrator’s passport and scan it when asked. Therefore administrators will be required to have two-factor authentication (TOTP specifically) enabled on their account for all integrations.

### Performance

ID will eventually run on Vulcan where it can run as a full server instead of server less but performance is fine right now.

### Maintenance

Any issues can be brought up to the maintainer. Any additional functionality can be added by deploying a new version.
