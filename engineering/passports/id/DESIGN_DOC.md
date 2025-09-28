# ID Design Doc

- **DRI**: [Jack](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/imthesquid.md)

## Objective

Create a universal authentication system for Purdue Hackers.

## Background

### Problem

Many Purdue Hackers projects necessitate keeping track of people’s identities (e.g. passports) or signing into an interface (e.g. issuing office). Instead of using external services Purdue Hackers should use their own internal system based around passports and make it available to anyone who wants to use it.

### Stakeholders

Anyone with a passport and all Purdue Hackers projects that require consistent identity tracking.

### Existing Solutions

- Continuing to use our self-hosted Authentik instance: High friction, does not fit the Purdue Hackers ethos of making our own solution for the fun of it

### Alternative Solutions

- Using public OAuthproviders (Google, Github): Have usage limits and other restrictions that would make them a pain to deal with.
- Integrate into Authentik: This is something that was considered but we would still rely on Authentik and this solution would likely end up with ID becoming irrelevant as more people would likely rely on Authentik's other options.

## Requirements

### Goals

- OAuth & [OIDC](https://openid.net/specs/openid-connect-core-1_0.html) compatibility
	- Usable with popular JS auth libs
	- Easy to implement
- Usable in a secure manner when necessary, configurable on a per-client basis
  - Some site could require 2FA for all sign ins and force users without it to add it before continuing
  - Use either TOTP or Webauthn (https://github.com/kanidm/webauthn-rs)
- Store passport data and manage which one is active for each user
- A user management interface
- Metrics and event logging (metrics exportable to some TBD software, events with a webhook)
  - Exact contents of metrics and event logging to be determined later
- Groups integration through OIDC spec (allows any application with the `user:read` scope to query a user's groups and take action on them)
- Future: Hook system, execute python code on certain events (ex. on:login, on:logout, on:usermanage) to modify data or deny request

### Non-Goals

- Be cryptographically secure with just passports (unnecessary when secure 2FA is available)
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

The user management system will allow a user to enroll/unenroll from 2FA and manage aspects of their profile as well as adding their own clients to work with ID (with some restrictions on scopes to protect sensitive information). The admin side will allow arbitrary user operations (enable/disable, see 2FA, etc).

The metrics and events system, groups, and (future) policies will be customizable from the admin dashboard.

### Deployment

Users can integrate with ID using the example repo as a base.

## Milestones

- User management
- Arbitrary user 2FA enrollment
- Advanced client management system
- Metrics and events active
- Groups API
- Future: Policies system

## Additional Considerations

### Security

Passports on their own are not secure since they just use basic NFC tags. For most applications this is fine but for high-security apps it is possible to swipe an administrator’s passport and scan it when asked. Therefore, apps can require two-factor authentication if they necessitate secure authentication but if the session is 2FA authenticated then the cached version will be accepted. If the session is not 2FA authenticated then an upgrade will be attempted.

### Performance

ID will eventually run on Vulcan where it can run as a full server instead of server less but performance is fine right now.

### Maintenance

Any issues can be brought up to the maintainer. Any additional functionality can be added by deploying a new version.
