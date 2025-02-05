# The Sign Design Doc

- **DRI**: @ImTheSquid

## Objective

Project the glory of Purdue Hackers with a monument of our logo, the glider from Conway’s Game of Life.

## Background

### Problem

Up to this point Purdue Hackers projects existed solely in the realm of software. While we were able to make very impressive apps and services, we needed something in the physical world as well. Hardware projects had never been attempted up to that point so exploration was necessary and we had a good idea for what it should look like.

### Stakeholders

Current and prospective Purdue Hackers members can interact with the Sign in multiple ways such as viewing it as a decorative piece (drawing attention for prospective members) or as an input to the receipt printer (increasing engagement with Hack Night).

### Existing Solutions

None, this is the first hardware project by Purdue Hackers.

### Alternative Solutions

- A smaller sign
- Flags
- Lightning time clock (which was merged into the Sign)

## Requirements

### Goals

- Take up the entire size of a window in Bechtel (about 1 meter)
- Display Lightning Time
- Be bright enough to see from outside
- Wi-Fi connectivity
- Self-updating

### Non-Goals

- True portability: Will require a wall outlet

### Constraints

- Initial extendable budget of $200
- Must be able to assemble with tooling we have access to (3D printing, basic soldering equipment)

## Design

### Physical

The physical design will be created in Fusion 360 then exported into whatever format is necessary for construction. A mechanical  engineering student will be consulted for design advice where necessary.

### User Interface

The only exposed user interface item is a light-up button. This will print to the receipt printer but could also be used to change profiles or do other tasks.

### Architecture

The Sign will first boot and initialize the LEDs as a status display. Once that happens it will immediately connect to Wi-Fi. After it establishes a connection it will check for firmware update (and if it finds one install and reboot) then start displaying Lightning Time.

## Milestones

- A month of design work
- Over a year and a half of building and debugging
- Blog post marks the completion of the project

## Additional Considerations

### Security

The Sign does not interact with any protected APIs. It only pulls software updates from the Purdue Hackers-managed `sign-firmware` repo which has restricted access.

### Performance

Code is written in Rust to be deployable to the restricted environment of an ESP32 while still being readable and maintainable in the future.

### Maintenance

The Sign is designed for low-to-no maintenance operation. It automatically restarts at any fault and can connect anywhere on campus. Whenever I graduate an update needs to be pushed with Wi-Fi credentials from a current student (preferably a freshman) to keep it connecting to the network by updating the secrets in the GitHub repository and bumping the crate version to prompt a rebuild.
