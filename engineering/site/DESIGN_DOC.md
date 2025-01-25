# Site Design Doc

- **DRI**: @letttttttuce

## Objective

The landing page for Purdue Hackers...

Design and build a user-friendly landing page for Purdue Hackers that embodies our unique brand and serves as a front-facing resource for people to learn more about the club (what we do and how to join) 
inform about our main events (hack night, community, ...)

tldr: tell everyone how cool we are

## Background

### Problem

- Current site is out of date, need a new updated site to reflect new branding and represent our online presence 
- Need a dedicated website to communicate what the club does and how interested individuals can get involved

### Stakeholders

- Primary Stakeholders: Prospective members, event sponsors, partner organizations, external collaborators
- Secondary Stakeholders: Club members, organizers

### Existing Solutions

- [Current Site](https://github.com/purduehackers/site)

### Alternative Solutions

?

## Requirements

### Goals

- Create an engaging and informative landing page to introduce the Purde Hackers to the public

- Highlight the club's mission, past projects, and upcoming events

- Provide a clear and user-friendly process for joining the club

- Ensure the site is mobile-friendly and accessible to all users

- Include contact information and links to the club's Discord, blog, social media channels, and other relevant resources

### Non-Goals

- Serve as a private dashboard or resource repository for current members
- Produce infinite gold
- Revive your grandmother

### Constraints

- The website must align with the club’s branding and visual identity
- Should be deployable using free or low-cost hosting services
- Should be easy to maintain and update with new content

## Design

### Architecture
- Frontend: Static website built with Next/React.js 
- Backend: Not required; content will be static or managed via a CMS (Sanity)
- Hosting: Vercel

### Implementation
- Modular, component-based structure
- Integration of third-party libraries when necessary (i.e. for 3D rendering, animations)


### Content
- Landing Page Content:
- Page sections: Hero, club overview, Hack Night (featured projects, passport cermonies?), community/workshops, blob, sponsorship info, call to action
- Event Fields: Fields: Title, date/time, location, description, RSVP link
- Contact Fields: Email address, social media links

### UI/UX Design
- Brand Figma: https://www.figma.com/design/3hvWVV9EF86eJJunNnN1w3/Designs?node-id=0-1&t=UTTgOYXRKbkijHh6-1
- Site Prototype: https://site-24.vercel.app/ 

### Deployment
Link Vercel Deployment

### Testing
- Test for mobile, cross-browser compatibility, accessibility

## Milestones

- 1: Finalize content structure, wireframes, and branding guidelines
- 2: Develop and test the homepage and navigation
- 4: Build additional pages (About, Events, Join Us)
- 5: Conduct user testing and make adjustments based on feedback
- 6: Launch website and promote on social media

## Additional Considerations

### Performance
- Optimize images and assets for quick loading times
-   (specify here) file types, rendering pipeline etc etc
- Leverage static site generation for fast page delivery

### Maintenance
- Designate club organizers to update content periodically (e.g., events, contact information)
- Conduct (some period, annual?) reviews to refresh design and content

## References

> Optional. Links to any external resources that are relevant to the project.
