# PDF Concat Design Doc

DRI: [Ray](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/rayhanadev.md)

## Objective

This is a script will concatenate [Passport](/engineering/passports/README.md) Data Pages in a single PDF file.

## Background

### Problem

When printing Passport Data Pages, it takes forever to find the R2 bucket URL for each file, join them all together into
a single file, and print them all. It is also wasteful to print each page individually.

### Stakeholders

Officers in Purdue Hackers who are responsible for printing Passport Data Pages for [Prep](/events/passport-ceremonies/prep.md)

### Existing Solutions

Manually guess the R2 bucket URL for each page and download them individually. Then use a tool like [ilovepdf.com](https://www.ilovepdf.com/merge_pdf)
to merge them into a single PDF file.

### Alternative Solutions

1. Create an API endpoint that will generate the PDF file.
2. Create a worker that will generate the PDF file prior to the ceremony.

## Requirements

### Goals

- Allow users to easily download a script.
- Allow users to select a range of pages to concatenate.
- Concatenate the pages into a single PDF file.
- Provide the final PDF file to the user.

### Non-Goals

- Provide a UI for the script.
- Provide a way to print the PDF file.

### Constraints

- The script must be run on a machine with access to the internet.

## Design

Create a script that will fetch the data for the passport pages in a range from `<start>` to `<end>`, render the pages,
and convert the render into an image. Then concatenate the images into a single PDF file and provide the final PDF file

1. Fetch data for passport pages in a range from `<start>` to `<end>`
2. Render the pages (similar to [purduehackers/passport-issuing-office](https://github.com/purduehackers/passport-issuing-office/blob/main/lib/generate-data-page.tsx))
3. Convert the render into an image
4. Concatenate the images into a single PDF file
5. Provide the final PDF file to the user

### Architecture

- **Language**: TypeScript (Bun)
- **Dependencies**: `sade`, `satori`, some PDF library

### Data Flow

1. Fetch Data
2. Render Data
3. Convert Render to Image
4. Concatenate Images
5. Provide PDF File

### Error Handling

- If the script fails to do something, it will log the error and exit.

### Testing

- The script will be tested manually by running it on a machine with access to the internet.
- Can add unit tests if necessary.

## Milestones

- Start Date: September 28th, 2024
- Milestone 1 - Fetch and Render Data: September 29th, 2024
- Milestone 2 - Convert Render to Image: September 30th, 2024
- Milestone 3 - Concatenate Images: October 1st, 2024
- Milestone 4 - Provide PDF File: October 2nd, 2024
- Milestone 5 - Documentation: October 3rd, 2024
- End Date: October 5th, 2024

## Additional Considerations

### Security

This script will not store any data. It will only fetch the data, render it, and provide the final PDF file to the user.

### Performance

Not a concern for this project.

### Deployment and Maintenance

The script will be deployed to GitHub and maintained by the DRI. It will be run during Prep prior to the ceremony, and
if there are any issues, the DRI will be responsible for fixing them.

## References

- [Passport Issuing Office](https://github.com/purduehackers/passport-issuing-office)
