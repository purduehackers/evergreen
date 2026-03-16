<!--
    Please note this template is only meant to be used in the context of engineering.
    If you are a non-engineer, please reference other documents within your respective
    division for a better idea of a documentation standard. Non-engineering projects
    should not use this template.
-->

# Events Design Doc

- **DRI**: @ericswpark

## Objective

Display and manage all events hosted by Purdue Hackers.

## Background

### Problem

Events hosted by Purdue Hackers need to be recorded so that people can look back
on what events we've hosted, as well as keep track of upcoming events. We should
have our own events site that manages this flow instead of using 3rd party
event management platforms.

### Stakeholders

All event attendees of Purdue Hackers

### Existing Solutions

- The current events site is already complete for past events.
- We are currently using Luma for future events.

### Alternative Solutions

- Continue to use Luma and show upcoming events via an API. There has been some
  reluctance in the continuation of use of Luma.

## Requirements

### Goals

- Show past events in a timeline view
- Display all upcoming events
- Allow people to RSVP to events
  - Allow people to receive email notifications
  - Allow people to receive text notifications
- Allow organizers to manage events
  - Create/delete/reschedule events
  - View RSVP count
  - Send out notifications through different channels
  - Write up event retrospectives
    - Upload images for event retrospectives
    - Show statistics (ex: **3** new Rust projects, **48** people joined the Systems Session, etc.)


### Non-Goals

- Keep track of live attendee count (should be a separate project tied to attendance)

### Constraints

- Must be hosted on a platform we own
- Should not use 3rd party event management platforms like Luma

## Design

### Architecture

The majority of our codebase will be written on AstroJS, with PostgreSQL serving
as our database. AstroJS will contain the fullstack
application that attendees and organizers will use to manage and view events.

### User Interface

The user interface will be a website. Users will view events through their browser.
Emails and texts will be setn out for RSVP notifications that will redirect to
the website once clicked.

### Deployment

Vulcan will host the PostgreSQL database, while Vercel will host our fullstack
AstroJS application.


## Milestones

- Migrate all events data from AstroJS content collections to PostgreSQL
- Create admin portal
- Integrate admin portal with ID
- Allow for writing retrospectives from admin portal
- Allow for creating new events from admin portal
- Allow for event management from admin portal
- Create RSVP component
- Integrate with an external service (ex: Mailchimp) for email notifications
- Integrate with an external service (ex: Twilio) for SMS notifications
- Allow for admin portal to send out notifications

## Additional Considerations

### Security

The admin portal will have to be sufficiently protected. For authentication, we will
use Purdue Hackers' ID system, but we should take precautions so that only organizers
can manage and create new events. In addition, we should take care not to expose
mailing lists or phone number lists, if we do end up collecting them for the purposes
of RSVP only.

Events data is meant to be public, so there are no additional security considerations.

### Performance

With the current events site displaying past events, the performance is excellent
as AstroJS compiles to a static website. As we move to a database, we should monitor
the usage and make adjustments as necessary.

### Maintenance

This project will be collectively maintained by organizers and Hack Bishops of
Purdue Hackers.

## References

https://events.purduehackers.com
