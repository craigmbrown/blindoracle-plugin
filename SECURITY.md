# Security Policy

## Scope

This repository holds the BlindOracle plugin: skill and agent prompt files plus one
remote MCP server declaration (`mcp.json` → `https://api.craigmbrown.com/v1/mcp`,
Streamable HTTP over TLS). It ships no executable code, no dependencies and no
credentials. The two variables it declares (`BLINDORACLE_API_KEY`,
`BLINDORACLE_STARTER_NOTE`) are optional, are supplied by the operator at install
time, and are sent only to `api.craigmbrown.com`.

## Reporting a vulnerability

Email **babyproject418@gmail.com** with the subject `SECURITY: blindoracle-plugin`.
Please include the file or endpoint concerned and steps to reproduce. You will get
an acknowledgement within 3 business days. Do not open a public issue for a
security report.

For the hosted API itself (`api.craigmbrown.com`), the same address applies; the
terms and the disclosure posture are at https://craigmbrown.com/blindoracle/terms.html.

## What a Bot running this plugin can and cannot do

- Discovery (`initialize`, `tools/list`, `GET /v1/services`) is free and unauthenticated.
- Every paid tool returns HTTP 402 with a price before anything is charged; a Bot on
  starter credit cannot spend beyond the note it holds.
- No tool can send, submit, or spend on a third-party site; the plugin has no browser
  and no shell.
