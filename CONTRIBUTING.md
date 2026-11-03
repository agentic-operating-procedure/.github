# Contributing

This guide applies to every repository in the `agentic-operating-procedure` organisation.

## The first rule

Every repository in this estate owns exactly one class of artefact. Before you change anything, establish which repository owns it, and change it there. A change made in the wrong repository is not a small mistake: it creates a second authority for the same artefact, and the second authority is the one people will find.

## Change classes

The governance process distinguishes five classes of change. Each has a different review path.

| Class | What it changes | Where it is filed | What it requires |
|---|---|---|---|
| Foundational | The meaning of a defined term, the shape of the hierarchy, a non-goal | `aop-governance` as a change request | Programme owner approval, and a cascade impact assessment across the estate |
| Normative specification | A requirement, a schema, a conformance clause | The repository that owns the specification | Technical review against the specification's own conformance clauses |
| Architectural | An interface contract, a boundary, a topology | The repository that owns the architecture | Technical review, with the affected implementations listed |
| Implementation | Code, tooling, fixtures, harnesses | The owning repository | Peer review, passing verification, and a demonstrated result |
| Research | A question, a hypothesis, a protocol, a finding | The owning repository | Peer review of method, and separation of finding from adopted conclusion |

A change that touches more than one class is split before it is reviewed. Reviewing a mixed change means reviewing the weakest part of it.

## Where to file

| You want to change | File it in |
|---|---|
| A defined term, a level of the hierarchy, a non-goal | `aop-governance`, as a change request |
| The estate structure, the repository map, the phase plan | `aop-governance`, under `plans/` |
| A normative requirement or schema | The repository that owns that specification |
| The organisation profile, templates, contribution policy | `.github` |
| Code, tooling, or a fixture | The repository that owns that code |

## Branching

Branch from `main`. Never commit directly to `main`.

| Prefix | Use |
|---|---|
| `feat/` | A new artefact, a new capability, a new document |
| `fix/` | A correction to existing content |
| `docs/` | A documentation change that alters no meaning |
| `chore/` | Maintenance that changes no artefact: dependencies, tooling, configuration |

Branch names are lowercase with dashes: `feat/wave-1-governance-seed`.

## Commits

A commit message states what changed and why, in one line for the subject and a paragraph for the body when the why is not obvious.

```
feat: author the Wave 1 governance seed for aop-governance

The governance seed carries the programme plan, the repository map, the
cascade checklist, the concept model, and ADR-0001 through ADR-0010.
```

Do not write "update files", "fix bug", or "WIP". Do not squash-fixup rebase into a single commit before review; the reviewer needs the steps.

## Pull requests

Every change lands through a pull request.

1. Branch from `main` and push.
2. Open the pull request against `main`.
3. Fill in the template completely. An unfilled template is a rejected pull request.
4. Link the issue it closes, if there is one.
5. Request review.

The pull request body must state:

- Which change class it is, and why.
- Which repository owns the artefact being changed.
- How it was verified, with the actual output. A claim of passing verification without the output is not verification.
- What it breaks or supersedes, including any downstream repository affected.

## Merge policy

| Merge method | When |
|---|---|
| Squash merge | Documentation, configuration, and content-only changes |
| Merge commit | Changes with meaningful intermediate history: a spec built in steps, a refactor with distinct stages, an implementation with a reviewable sequence |
| Rebase merge | Never, for shared branches. Fast-forward-only by direct push is permitted only when seeding a newly created repository, where no base branch exists to compare against |

Linear history is required. The merge commit that records a reviewed decision is itself the audit record.

## Branch protection

`main` is protected in every repository in the estate. Direct pushes are rejected, except when seeding a newly created repository. A pull request with at least one approving review is required to merge. The branch is deleted on merge.

## Labels

Every repository uses one five-label authority gradient. The label states the authority of the artefact, not the workflow state of the issue.

| Label | Meaning |
|---|---|
| `research-proposal` | Under consideration. No authority. |
| `draft-spec` | Provisionally accepted. Not yet normative. |
| `release-candidate` | Fully specified and ready to become normative. |
| `stable` | Normative and authoritative. |
| `deprecated` | Superseded. Kept for the record, no longer authoritative. |

Do not invent additional labels without a change request against `aop-governance`.

## Writing rules

These are checked automatically before a push, and a violation blocks the merge.

- No en-dash, em-dash, or three-em character. Use a colon, or join with "to", "and", or a semicolon.
- No reference to a closed or restricted standards body. Cite ITU-T, ETSI, ISO and IEC, or NIST.
- Every artefact title states its type and the full span of the levels or scope it covers.
- Every published artefact carries its version, its status, its scope, and its owner.
- Every internal link resolves. A link to an artefact that does not exist is a defect.

## Review expectations

Reviewers check three things, in this order:

1. **Is this in the right repository?** A correct change in the wrong repository is still a defect.
2. **Does it change meaning?** If it alters a definition, a requirement, an interface, or an authority boundary, it needs the corresponding change class and the corresponding evidence.
3. **Is it verified?** A change that cannot be demonstrated is a proposal, and it should carry the `research-proposal` label rather than `stable`.

## Code of conduct

Participation is governed by `CODE_OF_CONDUCT.md`. Report unacceptable behaviour through a private security advisory.

## Security

Report vulnerabilities privately through a security advisory on the affected repository, per `SECURITY.md`. Do not open a public issue.
