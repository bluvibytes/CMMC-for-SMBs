# Security

## Design

This tool is built to be safe by construction for the kind of sensitive
context a defense contractor works in.

- **No network calls.** The tool makes no outbound requests. A Content
  Security Policy embedded in the file enforces this, including
  `connect-src 'none'`, which blocks network connections at the browser level.
- **No data collection.** There is no analytics, no telemetry, and no
  third-party script. Your answers stay in the page until you choose to save
  or export a file, which writes only to your own device.
- **No storage side channels.** The tool does not use cookies,
  `localStorage`, or `sessionStorage`. Closing the tab clears everything
  except the files you saved yourself.
- **Single file, no dependencies.** Everything is in `index.html`. There is
  no build step and nothing is pulled in at runtime, so there is no supply
  chain to compromise.
- **Output is sanitized.** User-entered text is HTML-escaped before display,
  and CSV exports guard against formula injection.
- **Content fingerprint.** Saved files and exports include a short
  non-cryptographic fingerprint of your answers so you can detect accidental
  or deliberate changes between versions. It is tamper-evidence, not a
  cryptographic signature, and is labeled that way in the tool.

You can verify all of the above by reading `index.html`, or by running the
tool with your network disconnected.

## Handling your data

Your saved files contain the information you entered, including company
details and notes about your environment. Treat them like any other internal
compliance document: store them somewhere access-controlled and share them
only with people who need them.

## Reporting a vulnerability

If you find a security issue in the tool itself, please report it privately
rather than opening a public issue. Email BluVi LLC at security@bluvi.ai. Include what you found, how to reproduce it, and
the browser and version you used.

Please allow a reasonable window for a fix before any public disclosure. This
is a small, free project maintained in good faith, and responsible disclosure
keeps users safe.

## Scope

In scope: the behavior of `index.html`, including any way it could leak data,
execute untrusted input, or mislead a user about their compliance status.

Out of scope: the security of your own device or browser, the accuracy of
third-party government sources linked from the tool, and decisions you make
based on the tool's output. The tool is educational and does not replace a
qualified assessment.
