# Contribution Guidelines

Thank you for taking an interest in improving this project! We encourage everyone to help improve this project with new features, bug fixes or performance improvements. Please take the time to read our guide to make this process faster and easier.

When contributing to this repository, first discuss the change you wish to make via RFC or any other method with the owners of this repository **before making a change**.

## Summary

- [Commiting](#commiting)
- [Submitting a pull request](#submitting-a-pull-request)

## Commiting

We recommend using [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) when writing your commit messages. This is because there is an excellent match when we use [Semver](https://semver.org/) to determine which will be the next version of the project (when automated with CI/CD we can generate automated and cohesive CHANGELOGs). A parallel of how this is related:

| Message               | MAJOR.MINOR.PATCH | Semver |
| --------------------- | ----------------- | ------ |
| feat!: message        | `x`.0.0             | MAJOR  |
| feat(scope)!: message | `x`.0.0             | MAJOR  |
| feat: message         | 0.`x`.0             | MINOR  |
| chore: message        | 0.0.`x`             | PATCH  |
| build: message        | 0.0.`x`             | PATCH  |
| test: message         | 0.0.`x`             | PATCH  |
| ci: message           | 0.0.`x`             | PATCH  |

> 💡 The `x` indicates which part of the version will be incremented based on the commit message

Given a version number MAJOR.MINOR.PATCH, increment the:

- MAJOR version will be incremented when you make incompatible API changes;
- MINOR version will be incremented when you add functionality in a backwards compatible manner, and;
- PATCH version will be incremented when you make backward compatible tweaks and/or bug fixes.

A commit message can consists of a **header**, **body** and **footer**. The header is the only mandatory part and consists of a type and a subject. The body is used to fully describe the change. The footer is the place to reference any issues or pull requests related to the commit. That said, we end with a template like this:

```
<type>: <subject>

[optional body]

[optional footer]
```

To ensure that a commit is valid, easy to read, and changelog-ready, we have a hook that lints the commit message before allowing a commit to pass. This linter verifies the following:

- The header (first line) is the only mandatory part of the commit message;
- The body and footer are both optional but its use is highly encouraged;
- The header should contains:
  - A type:
    - Must be lowercase;
    - Must be one of:
      - **chore**: A change that neither fix a bug nor adds a feature;
      - **ci**: A CI change;
      - **docs**: A documentation change or fix;
      - **feat**: A new feature;
      - **fix**: A bug fix;
      - **test**: A test-related change.
  - A subject:
    - Must be limited to 50 characters or less;
    - Must omit any trailing punctuation.
  - The body:
    - Must have a leading blank line;
    - Each line must be limited to 72 characters or less.
  - The footer:
    - Must have a leading blank line;
    - Each line must be limited to 72 characters or less;
    - If your commit is about documentation or meta files, please add the tag **[ci skip]** to skip the building process.
    - If needed, reference to pull requests must be made here in the last line.

Example of a commit message (full):

```
type: commit message style guide for Git

The first line of a commit message serves as a summary.  When displayed
on the web, it's often styled as a heading, and in emails, it's
typically used as the subject. As such, you should specify a "type" and
a "subject". The type must be lowercase and one of: chore, ci, docs,
feat, fix, test. For the subject you'll need capitalize it and
omit any trailing punctuation. Aim for about 50 characters, give or
take, otherwise it may be painfully truncated in some contexts. Write
it, along with the rest of your message, in the present tense and
imperative mood: "Fix bug" and not "Fixed bug" or "Fixes bug".
Consistent wording makes it easier to mentally process a list of
commits.

Oftentimes a subject by itself is sufficient. When it's not, add a
blank line (this is important) followed by one or more paragraphs hard
wrapped to 72 characters. Git is strongly opinionated that the author
is responsible for line breaks; if you omit them, command line tooling
will show it as one extremely long unwrapped line. Fortunately, most
text editors are capable of automating this.

Issues and pull request can be referenced on the footer: #3 #12
```

Example of a commit message (short):

```
type: commit message style guide for Git #3 #12
```

## Submitting a pull request

Before submitting a pull request, please make sure the following is done:

- Clone (or fork) this repository and create your branch from `main` (e.g.: `feature-my-awesome-feature`);
- If you’ve fixed a bug or added code that should be tested, **add tests**;
- Ensure the test suite passes;
- Ensure your commit is validated;
