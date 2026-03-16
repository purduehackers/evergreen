# Evergreen Style Guide

This document serves to provide a set of guidelines for how to write good
documentation for Evergreen. This guide is less focused on the content and
more focused on the style and structure of the documentation.

## People

Whenever referring to someone in Evergreen, if they are a member of our
team and have an entry in [purduehackers/dark-forest](https://github.com/purduehackers/dark-forest)
then you should ALWAYS use the following format to refer to them:

✅ Correct

```markdown
[@rayhanadev](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/rayhanadev.md)
```

You should never not link to someone in dark-forest if they have an entry there
and you should never refer to someone by a handle besides their dark-forest
handle.

❌ Incorrect

```markdown
@rayhanadev
@someotherhandleforray
[Ray](https://github.com/purduehackers/dark-forest/blob/main/people/organizers/rayhanadev.md)
```

## Linking

When linking to other pages in the Evergreen documentation, you should always
use absolute links from the root of the repository. This is to ensure that
links do not break _toooooo_ hard when the documentation is moved around.

✅ Correct

```markdown
[Hack Bishops](/meta/structure/bishops.md)
```

❌ Incorrect

```markdown
[Hack Bishops](../structure/bishops.md)
[Hack Bishops](structure/bishops.md)
```

You should also always use the title of the page as the text for the link
if it is a page in the Evergreen documentation.

✅ Correct

```markdown
[Hack Bishops](/meta/structure/bishops.md)
```

❌ Incorrect

```markdown
[The Bishops Page](/meta/structure/bishops.md)
```

## Files and Folders

As long as it generally makes sense, you should always feel free to create
new files and folders in the Evergreen repository. Some general tips for when
to create new files and folders:

- If a page is getting too long, consider splitting it into multiple pages
- If a page is getting too complex, consider splitting it into multiple pages
- If aspects of a page can stand alone, consider splitting them into multiple pages
- If you are working on a project, consider creating a folder for that project

✅ Correct

```plaintext
/meta/structure/bishops.md
/meta/structure/divisons.md
/meta/structure/hierarchy.md
/meta/structure/roles.md
```

❌ Incorrect

```plaintext
/meta/structure.md
/meta/roles-and-divisons.md
```

## README.md vs Other Files

It is generally recommended to use `<project-name>/README.md` when creating a
new project in Evergreen vs. adding a `<project-name>.md` file. This is because
the README file is the first file that is displayed when you navigate to a
folder in GitHub and it is generally the first file that people will look at
when they are looking at a project.

You should create `<item>.md` files within a specific project folder for more
topics that are related to that project. A good example of this is the [Hack Night](/events/hack-night/README.md)
folder in the Evergreen repository.

✅ Correct

```plaintext
events/hack-night
├── README.md
├── attendance.md
├── badges.md
└── circles
   ├── README.md
   ├── data-science.md
   └── systems.md
```

❌ Incorrect

```plaintext
events
└── hack-night.md

events/hack-night
├── hack-night.md
└── circles
   └── circles.md
```

## Attribution

You should never write an attribution in Evergreen. This philosophy is because
we use Git/Github to track changes to the documentation and it is easy to see
who wrote what and when and get a clearer picture of the document's history.
Adding an attribution to a page is redundant and adds complexity to what needs
to be updated in documentation, therefore it is preferred that you do not add
attributions to pages.

✅ Correct

```markdown
# Hack Bishops
```

❌ Incorrect

```markdown
# Hack Bishops

Written by @rayhanadev
Last updated by @rayhanadev
```

## Images

When adding images to the Evergreen documentation, you should always add them
to a folder relative to the project. For example, if you are adding an image to
the [Hack Night](/events/hack-night/README.md) folder, you should add the image
to the `events/hack-night/images` folder, even if a subfolder is using the image.

✅ Correct

```plaintext
![Hack Night](/events/hack-night/images/hack-night.png)
```

❌ Incorrect

```plaintext
![Hack Night](https://example.com/hack-night.png)
![Hack Night](/images/hack-night.png)
```
