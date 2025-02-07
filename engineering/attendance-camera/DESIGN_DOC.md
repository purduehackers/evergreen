# Attendance Camera Design Doc

> ⚠️ THIS IS A DRAFT PROPOSAL. It is open to be claimed by anyone interested.

- **DRI**: UNCLAIMED

## Objective

Surveillance state @ Hack Night.

## Background

### Problem

Taking attendance is a very manual process that can interrupt the flow of Hack Night. The attendance camera would automate this process by automatically counting incoming and outgoing Hack Night attendees in a private and secure way.

### Stakeholders

Organizers who take attendance.

### Existing Solutions

- [Tabulus](/engineering/tabulus/README.md)
	- Still requires manual counting

### Alternative Solutions

- Attendance drone
	- Cool but very complicated
- Attendance roomba
	- Will get stuck on a cord or a badge idk

## Requirements

### Goals

- Count the incoming and outgoing Hack Night attendees automatically on a rolling basis
- Show data in a spreadsheet or dashboard
- Send occasional data to Google for targeting advertising (new revenue stream)

### Non-Goals

- Send data to the US government (for now)

### Constraints

- All computation must happen on the gadget or Vulcan
- Privacy must be preserved

## Design

The physical implementation will consist of a Raspberry Pi and a camera on top of the ledge facing the main staircase. It will be able to see people going up or down the stairs.

The computation will happen either on the Pi or on Vulcan. It will output data to a source that can be analyzed by organizers.

## Milestones

- Acquire Pi and camera
- Create ML pipeline to count attendees
- Aggregate data in a database

## Additional Considerations

### Security

All computation will be local on Purdue Hackers-owned hardware. No PII will be stored.

### Performance

The pipeline will be processed on a computer with enough power to run it. This will probably be Vulcan.

### Maintenance

Maintenance should be minimal (aside from Wi-Fi credentials). Taking it out before Hack Night and putting it back afterwards is the only things necessary to do. Everything should auto-boot.
