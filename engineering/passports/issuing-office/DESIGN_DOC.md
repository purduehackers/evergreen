> This is a draft of a Design Doc for Passports/Issuing-Office.
> This doc is written from the perspective of a collaborator, months
> after this projects creation, and not the original project creator.
> Consider this document as informational rather than a direct source.

# Issuing Office Design Doc

[TODO(@ghost): Who, if anyone, is DRI?]
- **DRI**: UNCLAIMED

## Objective

Creating a first step interface for future and current passport holders to design and register their passport, to be created in an upcoming passport ceremony.

## Background

### Problem

With the creation of the Purdue Hackers passport, a method of creating and managing passport data pages usable by members of the community was needed. Data page creation and management needed to be simple and convenient for future passport holders.

### Stakeholders

Anyone who wishes to become a passport holder, and anyone with a passport who wants to view a digital representation or update their date page with the creation of a superseding passport.

### Existing Solutions

No existing solution is presented, as this project is a core piece of the passports project. The closest "existing" solution is manual creation of passports using SQL queries directly interfacing with [ID](/engineering/passports/id/README.md)'s passport database.

## Requirements

### Goals

- Allow users to easily generate a passport data page.
- Manage user data through an OAuth connection for logins.
- Generate a printable image for use in a passport ceremony.
- Record data page information in the core passport database.
- Permit management of Passport Ceremonies (Creation, Modification, Deletion).
  - This should be accessible to "Admin" role users as deemed by their role in [ID](/engineering/passports/id/README.md).

[TODO(@ghost): Add Non-Goals]
### Non-Goals
- 

### Constraints

- The script must be run on a machine with access to the internet.
- Authentication must be completed using an external provider, as passport creation cannot require a passport.

## Design

[TODO(@ghost): Add Design Blurb]

### Architecture

- **Language**: TypeScript (NextJS / React)
- **Dependencies**: `prisma`, `react`

### Error Handling

- If passport generation fails, an alert should be placed clearly on screen.
- If OAuth authentication fails, authentication should be re-prompted.


## Milestones

[TODO(@ghost): Add Milestones]

## Additional Considerations

### Security

All authentication and data management should be done through Discord OAuth and [ID](/engineering/passports/id/README.md). Passport data pages are publicly accessible via an R2 bucket and should *not* be considered secure, private, or otherwise protected.

### Performance

Performance is not a great concern, however any user-facing task that takes more than a few seconds to complete should provide feedback to the user of progress.

### Deployment and Maintenance

The site will be deployed to Vercel and maintained by the DRI. When passport ceremonies are created or otherwise modified, they can be managed by an Admin role user via the `/admin` endpoint.