# financeBRO Design Doc

- **DRI**: [@joshamstutz](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/joshamstutz.md)

## Objective

Design and build a new finance automator for Purdue Hackers to help track expenses/credits as well as automate reimbursements.

## Background

### Problem

- Current finances are not tracked... not easy to quickly know our budget
- Reimbursements take forever/are annoying

### Stakeholders

- Primary Stakeholders: President/Treasurer
- Secondary Stakeholders: Organizers

### Existing Solutions

- Manually check finances/reimburse

## Requirements

### Goals

- Create an automator that will track finances for organizers
- Automate reimbursements

### Non-Goals

- Make one bajillion dollars
- Become employed

### Constraints

- The bot must be able to interact with Purdue's reimbursement portal
- Must be self-sufficient for the most part

## Design

### Architecture

- "Frontend": Discord, Google Sheets
- Backend: Python

### Commands

- /add - adds an expense/credit to our finances spreadsheet
- /remove - removes the most recent entry to the spreadsheet
- /budget - shows the total money left (starting budget + credits/expenses)
- /authorize - marks the "authorized" field "Y" (will act as 2-factor-auth before /reimburse can be used)
- /find - returns the ID, "authorized", and "reimbursed" data of a record given the name, memo, and amount of the record
- TODO: /reimburse - duh

## Milestones

- Created - January 2025
- Launched - TBD

## Additional Considerations

### Maintenance

- Occasional debugging/spreadsheet manual editing
- Adding any necessary new commands

## References

-[sheet template](https://docs.google.com/spreadsheets/d/1n6epUDNWOAmZClTKRHU1Ot_iVdGyYdDtgPNYTq5AZdA/edit?usp=sharing)

## **TODO**

- Launch
- Figure out reimbursement automation
- Make a bajillion dollars (always a todo)
