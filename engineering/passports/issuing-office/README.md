# Passport Issuing Office

This is the web frontend for Passport Creation and Passport Ceremony management.

## Quick Links

- [Live Website](https://passports.purduehackers.com)
- [Github Repo](https://github.com/purduehackers/passport-issuing-office)
- [Design Doc](/engineering/passports/issuing-office/DESIGN_DOC.md)

## Key Information

- **Status**: Active
- **Maintainer**: UNASSIGNED

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/purduehackers/passport-issuing-office.git
cd passport-issuing-office
```

2. Install the dependencies:

```bash
pnpm install
```

3. Run it locally:

```bash
pnpm dev
```

## Testing Changes on Vercel

The [Live Website](https://passports.purduehackers.com) is hosted on the [Vercel](https://vercel.com) platform. When you create a Pull Request, Vercel will automatically build a preview of your changes (If you are a first time contributor, a current maintainer will need to approve this) and provide you with a URL to view these changes.

If you are unable to view the preview URL, or if you need to change environment variables, you may have to request access to the Purdue Hackers organization on Vercel. Ask for assistance in the [#passports](https://discord.com/channels/772576325897945119/1153709641839161454) Core channel or contact the current DRI.

If you are unable to sign in with Discord on the preview site, and you need to sign in to test, ask for assistance in the [#passports](https://discord.com/channels/772576325897945119/1153709641839161454) Core channel or contact the current DRI. Someone will need to add `https://{Preview URL}/api/auth/callback/discord` to the OAuth2 Scopes of the Wack Hacker Discord Bot.

## Troubleshooting

If you encounter any issues, please create an issue on the [Github Repo](https://github.com/purduehackers/passport-issuing-office/issues). If you think you can fix the issue, open a [Pull Request](https://github.com/purduehackers/passport-issuing-office/pulls)!