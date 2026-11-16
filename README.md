<p align="center">
  <strong>MBACP_Q</strong><br />
  Benchmark instances for balanced and multi-curriculum academic planning problems.
</p>

<p align="center">
  <img alt="Text data" src="https://img.shields.io/badge/format-text-2f6f4e" />
  <img alt="Curriculum planning" src="https://img.shields.io/badge/domain-curriculum%20planning-444444" />
</p>

<p align="center">
  <code>BACP</code> | <code>Curriculum Planning</code> | <code>Prerequisites</code> | <code>Optimization</code>
</p>

---

`mbacp_q` contains benchmark data for the Balanced Academic Curriculum Problem and multi-curriculum variants. The files describe periods, courses, academic load information, and prerequisite relationships.

The repository provides input data only. It does not include a solver, parser, or experiment runner.

## Product Surface

| Area | Contract |
| --- | --- |
| Runtime | None; static benchmark files |
| Data format | Plain-text curriculum sections |
| Data path | External model or parser reads files directly |
| Storage | Git-tracked text files |
| Documentation | This README |
| Distribution | GitHub repository |

## Runtime Shape

```mermaid
flowchart LR
  researcher["Researcher"] --> repo["MBACP_Q"]:::primary
  repo --> files["BACP and MBACP files"]
  files --> model["Curriculum optimization model"]

  classDef primary fill:#2f6f4e,stroke:#173927,color:#ffffff,stroke-width:2px
```

## Responsibilities

- Preserve base BACP instances and combined multi-curriculum instances.
- Store course, period, load, and prerequisite information in plain text.
- Keep instance naming meaningful for source-curriculum combinations.
- Leave solution methods and parser implementation to downstream projects.

## How It Is Built

| File Pattern | Role |
| --- | --- |
| `bacp8`, `bacp10`, `bacp12` | Base BACP instances. |
| `bacp*_1`, `bacp*_2` | Variant instances. |
| `mbacp*.txt` | Multi-curriculum or combined instances. |
| `README.md` | Data contract and repository documentation. |

## Platform and Service Dependencies

<table>
  <tr>
    <th>Service / Object</th>
    <th>Provider</th>
    <th>Usage</th>
    <th>Purpose</th>
  </tr>
  <tr>
    <td><code>bacp*</code> and <code>mbacp*</code></td>
    <td>Repository files</td>
    <td>Read by academic curriculum optimization models.</td>
    <td>Provides reproducible benchmark inputs for load balancing and prerequisite constraints.</td>
  </tr>
</table>

## File Structure

Representative files use section markers such as:

- `# P`: Number of periods.
- `# C`: Course data with identifiers and load-related values.
- `# R #`: Prerequisite relationships.

Some filenames encode the source curricula used to build a combined instance.

## Verification

No automated tests are defined. Recommended manual verification is to parse one base instance and one combined instance before running a full experiment batch.

## Secret Handling

The repository contains benchmark curriculum data only and should not store private student records or credentials.

## Errata (2026-11)

- `mbacp123.txt`: the header listed `bacp8_1`, `bacp10_2`, `bacp12_2`, but the quotas, the `Total:118`/`Shared:25` counts and the instance description (46, 42 and 66 courses) correspond to `bacp8`, `bacp10` and `bacp12`. The header now lists `bacp8`, `bacp10`, `bacp12`.
- `mbacp_3_04(8_1x11_1x12_2).txt` was renamed to `mbacp_3_04(8_1x11_1x12_1).txt`: the file has always used `bacp12_1`, and its quotas correspond to that curriculum.
