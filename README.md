# .github

Organisation-wide assets for `agentic-operating-procedure`. This repository holds the public front door and the automation that every other repository in the estate inherits.

| Field | Value |
|---|---|
| Authority | Organisation profile, contribution policy, issue and pull-request templates, organisation-wide automation |
| Tier | Governance |
| Landing wave | 1 |
| Version | 0.1.0 |
| Status | Stable |
| Licence | MIT |

## What this repository owns

- The organisation profile README, rendered on the organisation page.
- The contribution guide, the code of conduct, and the security policy.
- The issue and pull-request templates inherited by every repository in the estate.
- The repository defaults, topic conventions, and the label scheme.

## What this repository does not own

- Any artefact that belongs to a single domain repository. The governance seed lives in `aop-governance`, not here.
- The estate structure itself, which is recorded in `aop-governance` under `plans/`.

## Layout

```
.github/
  README.md                        # this file
  CODE_OF_CONDUCT.md               # conduct policy
  CONTRIBUTING.md                  # contribution guide, with the review and merge doctrine
  CODEOWNERS                       # ownership declaration
  SECURITY.md                      # vulnerability reporting policy
  LICENSE                          # MIT
  PULL_REQUEST_TEMPLATE.md         # inherited by every repository in the estate
  .github/
    ISSUE_TEMPLATE/                # inherited by every repository in the estate
      aop-specification.yml
      aop-programme.yml
      aop-concept.yml
      issue.yml                    # general fallback
      config.yml
    workflows/
      label-drift.yml              # audits the five-label gradient across the estate
  profile/                         # the organisation profile
    README.md                      # rendered on the organisation page
    assets/
      aop-reference-architecture.png
```

GitHub discovers organisation-wide community health files only under the `.github/` directory of this repository. A template or a workflow placed at the repository root is not inherited by the estate.

## Labels

Every repository in the estate uses one five-label authority gradient. The label states the authority of the artefact it is attached to, not the workflow state of the issue.

| Label | Meaning |
|---|---|
| `research-proposal` | Under consideration. No authority. |
| `draft-spec` | Provisionally accepted. Not yet normative. |
| `release-candidate` | Fully specified and ready to become normative. |
| `stable` | Normative and authoritative. |
| `deprecated` | Superseded. Kept for the record, no longer authoritative. |

## Contributing

Read `CONTRIBUTING.md` in this repository first. It states the review and merge doctrine for the whole estate.

## Licence

MIT. See `LICENSE`.
