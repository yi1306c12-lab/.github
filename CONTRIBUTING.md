# Contribution Guide

The key words MUST, MUST NOT, SHOULD, and MAY are to be interpreted as described in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119).

## Development flow

1. Create an issue.
   - The body MUST state why the change is needed, not only what to do.
   - The title SHOULD be short enough to work as a branch name.
   - The title MUST NOT carry a Conventional Commits prefix.
2. Create the development branch.
   - The branch MUST be created by `gh issue develop`, so that it is linked to the issue. Ad-hoc branches are not used.
3. Open a pull request.
   - The title MUST carry a [Conventional Commits](https://www.conventionalcommits.org/) prefix.
   - The body MUST map each change to the part of the issue it addresses, rather than restating the issue.
   - Changes that fall outside the issue MUST be called out, with the reason they were needed.
4. Have it reviewed.
   - A pull request MUST be reviewed before it is merged.
5. Answer the review.
   - Every `(blocking)` item MUST be either applied or explicitly declined, by its number.
   - `(non-blocking)` items MAY be left as they are.
   - Items in `Tips` ask for nothing and need no answer.
6. Merge the pull request.
   - The merge method MUST be squash merge, and its commit message MUST be the pull request title.

## What a review looks like

A review has two sections, in this order: `Requested changes`, then `Tips`.
Keeping them apart is the point; mixing them makes a review impossible to answer point by point.

Both sections follow [Conventional Comments](https://conventionalcomments.org/).
Items in `Requested changes` open with `<n>. <label> (<decoration>): <subject>`, numbered continuously across the section, so that each item can be answered by its number.
Items in `Tips` open with `<label>: <subject>` and carry no decoration.

A section with no items states that there is nothing to report.

### `<label>` and `<decoration>`

`<label>` says what kind of remark it is.
`<decoration>` says how strongly it is being asked for.
Both are taken from the tables below.

| label | meaning | section |
| --- | --- | --- |
| `issue` | something is wrong and has to change | Requested changes |
| `suggestion` | a concrete alternative worth adopting | Requested changes |
| `question` | an answer is needed before the change can be judged | Requested changes |
| `nitpick` | preference only; declining it costs nothing | Requested changes |
| `note` | background, operational detail, or a point checked and found fine | Tips |
| `praise` | something worth keeping as it is | Tips |

| decoration | obligation on the author |
| --- | --- |
| `blocking` | the pull request is not merged until this is applied or explicitly declined |
| `non-blocking` | the pull request can be merged as it is; the item may be handled later or not at all |

## Language

Anything posted to GitHub — issue bodies, pull request bodies, reviews, comments — MUST be written in Japanese.

Identifiers MUST be English regardless of the language around them: resource names, branch names, issue titles, and pull request titles.
An issue title becomes a branch name through `gh issue develop`; a pull request title becomes the squash commit message.

A file tracked in a repository MUST be written in the language of its readers:

- **English**: files read together with the tooling that consumes them.
  - code
  - configuration
  - instruction files
- **Japanese**: prose written for people.
  - top-level `README.md`
  - everything under `docs/`

A file that matches both MUST be English; the tooling audience wins.