# Attendance Bot (Tabulus) Design Doc

- **DRI**: @stopwatchtt

## Objective

The goal of this project is creating a Discord bot that can help keep track of attendance at Hack Night.

## Background

### Problem

> Keeping track of attendance during Hack Night requires people to remember to take attendance, and people are prone to forget to do so.
> Usually attendance is stored by noting a headcount in an attendance thread. Making the thread and sorting through the data is annoying to do by hand.
> Currently we do not have a very accessible central storage location for attendance data, except for threads on Discord, but that is not conducive to being analyzed.

### Stakeholders

> This project is primarily useful for organizers. It would allow organizers to analyze when attendance peaks, when attendance dies down, how this changes per hack night, and therefore allow organizers to predict future attendance.

### Existing Solutions

> The current solution is for an organizer to manually open a thread in Discord in the attendance threads forum. Organizers then have to remember periodically throughout the night to go and perform a headcount.

### Alternative Solutions

> Organizers have done a lot of brainstorming around devices that could help track the number of people physically at hack night but all potential options are vastly outside the scope of what this project would do and require.

## Requirements

### Goals

> Can create threads upon request (or potentially automatically per Hack Night)
> Allow users in a thread to type a single number and have that value be saved.
  > The bot should provide active confirmation whenever this happens.
> For all members that are joined into the current attendance thread, the bot should ping everyone within that thread every hour to request an attendance headcount.
  > Likely this will be adjusted to "after an hour of inactivity ping everyone in the thread"
> Command to "end" hack night and save the time when that happens. The bot will stop taking attendance until next hack night.

### Stretch Goals
> Full functionality for accessing a database of each hack night with the corresponding attendance values.
  > Capability to request a line plot of the current hack night attendance
  > Capability to request a readout of each individual attendance value and the time it was taken
  > Capability to adjust 

### Non-Goals

> What will this project not achieve?
> Define the scope of the project to prevent scope creep.

### Constraints

> Any limitations that the project must function within that aren't
> immediately obvious.

## Design

> How will this project be implemented? This section is more freeform and can vary
> by person and project. Some suggested sub-headings:
> - Architecture
> - Implementation
> - Data Models
> - User Interface
> - Deployment
> - Testing

## Milestones

> Rough estimate of the timeline for the project. This can be broken down into
> smaller milestones if needed. Can be dates or Hack Nights.

## Additional Considerations

### Security

> Security concerns and how they will be addressed. (Optional)

### Performance

> Performance needs and how they will be addressed. (Optional)

### Maintenance

> How will this project be maintained? Who will be responsible for it after
> rollout?

## References

> Optional. Links to any external resources that are relevant to the project.
