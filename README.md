# RCO-A2A — Regulatory Compliance Objects (protocol layer)

Signed, deterministic, machine-verifiable compliance state per object per jurisdiction — resolved upstream and served over MCP and A2A. Agents consume the result of the rules, not the rules.

This repository is the MIT **protocol layer**: the record schema, rule-set schema, issuer-registry schema, tool contract, signature profile test vectors, the fleet manifest and the published pair list. Anyone may implement the shape.

- MCP: `https://mcp.rco-a2a.ai/mcp` — `resolve_compliance`, `get_record`, `list_rule_sets`, `list_issuers` (read-only, no auth, typed errors)
- Door: https://rco-a2a.ai · GSC rail: https://rco-a2a-bpc.ai · partner rail: https://rco-a2a-cpg.ai
- Records verify from the `gsc-rco-2026-08` key on https://dpuone.ai/.well-known/jwks.json, rooted in the signed issuer registry at https://consortium-10060.org/issuers.json
- Signature: detached JWS Compact (RFC 7515 + RFC 7797 `b64:false`), ES256 over the RFC 8785 canonical record — test vectors in `schema/v1.2/signature-test-vectors.json`

The GSC rail (records, rule sets, keys, fleet operation) is a proprietary GSC service. Operator: GreenCore Solutions Corp. · D-U-N-S 24-336-6774.
