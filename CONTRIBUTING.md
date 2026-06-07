# Contributing

Thank you for helping make CMMC easier and cheaper for small businesses to
understand. Contributions are welcome, whether that is a typo fix, a clearer
explanation, a bug report, or a correction backed by an authoritative source.

## Ground rules

This project lives or dies on its credibility, so a few principles are
non-negotiable.

1. **Authoritative sources only.** Every factual claim should trace to a
   primary government source: a `.gov` site, NIST, the CFR (eCFR), or NARA.
   Content corrections must cite one. Vendor blogs, forum posts, and summaries
   are not acceptable sources for a correction.
2. **Vendor-neutral.** No product placement, no affiliate links, no steering
   readers toward a particular paid service. The tool exists to inform, not to
   sell.
3. **Plain English.** Explanations should be understandable by a business
   owner who is not a security specialist. Define jargon the first time it
   appears.
4. **No overselling.** Do not add language that implies the tool certifies,
   guarantees, or replaces a professional assessment. It does not.
5. **House style.** Do not use em dashes anywhere in user-facing copy or
   documentation. Use commas, periods, or parentheses instead. This is checked.
6. **Keep it simple.** This is a deliberately minimal, single-file,
   dependency-free tool. Proposals that add frameworks, build steps, network
   calls, or tracking will be declined.

## How to contribute

### Reporting a problem

Open an issue using the appropriate template:

- **Bug report** for something that behaves incorrectly.
- **Content correction** for a factual or wording error. You will be asked for
  an authoritative source.
- **Feature request** for an idea, kept in line with the principles above.

For a security issue, do not open a public issue. See [SECURITY.md](SECURITY.md).

### Submitting a change

1. Fork the repository and create a branch.
2. Make your change in `index.html`. The tool is a single self-contained file:
   vanilla HTML, CSS, and JavaScript, no dependencies.
3. Verify it still works offline and that nothing introduces a network call.
4. Confirm there are no em dashes in your changes.
5. If you changed content, cite your source in the pull request.
6. Open a pull request using the template and describe what you changed and why.

### What to expect

This is a small project maintained by BluVi LLC alongside client work, so
reviews may take a little time. Corrections with a clear authoritative source
are the easiest to accept quickly.

## Code of conduct

Participation is governed by the [Code of Conduct](CODE_OF_CONDUCT.md). Be
respectful and constructive.

## Licensing of contributions

By contributing, you agree that your contributions to the code are licensed
under the Apache License 2.0, and your contributions to the content are
licensed under CC BY 4.0, consistent with the rest of the project.
