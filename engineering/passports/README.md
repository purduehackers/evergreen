# Passports

Passports are small, passport-like booklets that contain a data page and collection of stamp pages. They were created
with two goals in mind:

1. To provide a physical keepsake for hackers to remember their time in college.
2. To allow hackers to become "card-carrying members" of Purdue Hackers.

The projects within this folder are related to the creation and management of Passports. See [Passport Ceremonies](/events/passport-ceremonies/README.md)
for more information on the events where Passports are created.

## Quick Links

- [Dashboard](https://passports.purduehackers.com)
- [Blog](https://blog.purduehackers.com/posts/papers-please)
- [Design Doc](/engineering/passports/DESIGN_DOC.md)

## Key Information

- **Status**: Active
- **Maintainer**: [Matthew](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/hewillyeah.md)

## Projects

- [id](/engineering/passports/id/README.md): An OAuth2 server written in Rust that allows for Passports as a provider for authentication.
- [Passport Issuing Office](/engineering/passports/issuing-office/README.md): A web app written in TypeScript and Next.js that allows people
  to create Passports and register for Passport Ceremonies.
- [Passport Authority](/engineering/passports/authority/README.md): A mobile app written in Swift that allows organizers with Admin Passports
  to activate Passports at Passport Ceremonies.
- [Passport PDF Concat](/engineering/passports/pdf-concat/README.md): A script written in TypeScript that concatenates Passport Data Pages in
  a single PDF file for printing.
