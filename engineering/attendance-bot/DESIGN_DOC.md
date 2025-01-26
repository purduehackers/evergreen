# Attendance Bot (Tabulus) Design Doc

- **DRI**: @stopwatchtt

## Objective

The goal of this project is creating a Discord bot that can help keep track of attendance at Hack Night.

## Background

### Problem

- Keeping track of attendance during Hack Night requires people to remember to take attendance, and people are prone to forget to do so.
- Usually attendance is stored by noting a headcount in an attendance thread. Making the thread and sorting through the data is annoying to do by hand.
- Currently we do not have a very accessible central storage location for attendance data, except for threads on Discord, but that is not conducive to being analyzed.

### Stakeholders

- This project is primarily useful for organizers. It would allow organizers to analyze when attendance peaks, when attendance dies down, how this changes per hack night, and therefore allow organizers to predict future attendance.

### Existing Solutions

- The current solution is for an organizer to manually open a thread in Discord in the attendance threads forum. Organizers then have to remember periodically throughout the night to go and perform a headcount.

### Alternative Solutions

- Organizers have done a lot of brainstorming around devices that could help track the number of people physically at hack night but all potential options are vastly outside the scope of what this project would do and require.

## Requirements

### Goals

- Can create threads upon request (or potentially automatically per Hack Night)
- Allow users in a thread to type a single number and have that value be saved.
  - The bot should provide active confirmation whenever this happens.
- For all members that are joined into the current attendance thread, the bot should ping everyone within that thread every hour to request an attendance headcount.
  - Likely this will be adjusted to "after an hour of inactivity ping everyone in the thread"
- Command to "end" hack night and save the time when that happens. The bot will stop taking attendance until next hack night.

### Stretch Goals
- Full functionality for accessing a database of each hack night with the corresponding attendance values.
  - Capability to request a line plot of the current hack night attendance
  - Capability to request a readout of each individual attendance value and the time it was taken
  - Capability to adjust attendance values from the current hack night, primarily to fix errors (i.e. if someone types in the headcount wrong)

### Non-Goals

- The bot is going to be limited to Purdue Hackers specifically. Other organizations would have vastly different situational constraints.
- If Purdue Hackers does ever automate tracking how many people enter with physical hardware, it is unlikely that this bot will integrate with that functionality directly.

### Constraints

- it's currently hosted on my laptop whenever i feel like it and it needs to be moved to Vulcan lol - @stopwatchtt

## Design

- Developed in Python with uhhhh some discord bot package idr which tho
- Will be ran on Purdue Hackers' Vulcan server.
- Attendance data will be added to a csv file, which will be hosted... somewhere. Ideally somewhere on github. Need to work out specifics.

## Milestones

- Some time during Fall 2024: Bot was initially created.
- Hack Night 5.15: Bot code will be on Github.
- No later than the end of February 2025: the bot should be able to have all core functionality completed.

## Additional Considerations

### Security

- To protect the attendance data from tampering, the bot will likely need to look at user permissions and only allow organizers to add/alter any data.

### Maintenance

- DRI is @stopwatchtt. Once the project is on Github, anyone should be able to contribute changes.

## References

- None yet, but leaving this here for the future since there will be some stuff to put here eventually.
