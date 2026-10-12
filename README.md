# Klisten ToolGuard for Gemini CLI

Existing service: https://api.klisten.co.kr/mcp/toolguard

Only `toolguard_gate_check_paid` and `toolguard_attestation_get` are exposed. Gate calls are paid; existing attestation reads do not initiate scans. This integration does not execute tools, register targets, create scans, or guarantee safety.

Create your own restricted key at https://klisten.co.kr/app with gate:check / attestations:read and a spending limit. Store it using the host secret setting or a private environment variable. Never put a key into this package, a prompt, or a public repository. Do not use an operator's shared key in a multi-user agent.

Before a paid gate call, register the target and policy, satisfy scan/baseline requirements and fund your account. Confirm charge-bearing calls explicitly. Reuse the same idempotency key for an uncertain retry; never blindly retry with a new key.

Safe first test: list tools, then read an existing attestation belonging to your account. Do not invent identifiers or claim a missing record is a successful read.

Support: klisteninc@gmail.com
Privacy: https://klisten.co.kr/privacy.html
Terms: https://klisten.co.kr/terms.html
Guide: https://klisten.co.kr/customer-guide

## Install

```sh
gemini extensions install https://github.com/daehoonkwon-hash/klisten-toolguard-gemini-extension
```

Supply your own key only in the sensitive extension setting. See [INSTALL.md](INSTALL.md).

## Verification status — 2026-10-12

- Gemini CLI 0.63.0 isolated installation, authenticated `mcp list` connection, and uninstall: passed.
- Direct MCP initialize, tools/list and an existing attestation read: passed.
- Actual Gemini conversation tool invocation: NOT VERIFIED.
- No paid gate call was executed in this distribution test.
- Public repository availability does not mean gallery inclusion or Google endorsement.

