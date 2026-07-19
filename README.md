# platform-engineering-thesis

> Platform First: Why the AI Winners in Regulated Industries Will Be Built on Standard Engineering

A technology strategy thesis on the intersection of platform engineering, machine-readable compliance, and agentic AI in regulated industries.

## Read the thesis

[THESIS.md](./THESIS.md)

## The evidence

[EVIDENCE.md](./EVIDENCE.md) &mdash; The arithmetic of shared infrastructure.

A tool built to assess regulatory impact, not to prove this thesis, estimated
213 engineer-weeks pricing controls per system and 122 pricing shared
infrastructure once. Same obligations, same systems. That 43 percent gap is
the thesis expressed as a number &mdash; and it surfaced because the first
version of the tool made exactly the mistake this thesis warns against.

## Core argument

AI fails in regulated industries at the governance and data layer, not the model layer. That layer is platform engineering. The organizations that win the AI era in regulated financial services and manufacturing will not be the ones that deployed AI fastest. They will be the ones that built the governance, data, and platform infrastructure to make AI deployable at all.

Four claims:

1. AI inference costs are commoditizing. Model access is not a durable advantage. Organizational deployment capability is.
2. 72% of AI initiatives in regulated industries fail at the governance layer. That layer is classic platform engineering.
3. An agentic SDLC requires compliance enforcement at the pipeline layer. Narrative controls cannot be evaluated by an agent at 2am.
4. Rewriting narrative controls into machine-readable formats is the prerequisite for the agentic SDLC. These are the same idea from different angles.

## Related portfolio work

The thesis is grounded in working implementations:

| Repo | What it demonstrates |
|------|---------------------|
| [orbit-platform](https://github.com/brianpelow/orbit-platform) | 6-stage production services control plane with OPA policy engine |
| [cab-automation](https://github.com/brianpelow/cab-automation) | Automated CAB packages, risk scoring, and deployment gates |
| [mcp-compliance-grc](https://github.com/brianpelow/mcp-compliance-grc) | SOC 2, ISO 27001, and PCI-DSS control mapping and evidence generation |
| [fintech-platform-reference](https://github.com/brianpelow/fintech-platform-reference) | Reference architecture with SOX/PCI-DSS/FFIEC control mappings |
| [platform-conductor](https://github.com/brianpelow/platform-conductor) | Governance scorecard: Level 5/5, 96.4/100 across 22 repos |

## Version history

| Version | Date | Changes |
|---------|------|---------|
| v3 | May 2026 | Added losing trajectory, expanded phased implementation guidance |
| v2 | May 2026 | Added cost quantification, liability caveat, infrastructure stack, compounding advantage |
| v1 | May 2026 | Initial draft |

## License

Creative Commons Attribution 4.0 International