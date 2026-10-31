# Replication Package

This package accompanies the paper. It contains the materials for the paper's two data sources.

| File | Contents |
|------|----------|
| `data/` | The coded proposed change dataset: one YAML file per incident report (`1.yaml` to `75.yaml`), 362 action items in total. |
| `action-type-coding-guide.md` | The guide we used to code action type, the polarity axis of the Evolutionary Response Matrix, with worked examples. |
| `interviews.md` | The interview protocol, the codebook that connects our codes to the theory, and a table linking each interview quote in the paper to its interview. Transcripts are not shared (see the file for why). |

## Proposed change dataset (`data/`)

Each file holds the action items from one public incident report in the Verica Open Incident Database (VOID). A comment block at the top of each file gives the organization, the URL of the incident report, and a short description of the incident. Each action item is a top-level key (`AI-1`, `AI-2`, ...). Above its fields, a comment quotes or paraphrases the passage of the incident report the item comes from.

### Fields

Fields from the prior study that this dataset extends:

| Field | Meaning |
|---|---|
| `experience` | What happened in the incident that motivated the item. |
| `action` | What the item proposes to do. |
| `target` | The part of the system the item changes. |
| `goal` | The intended outcome. |
| `lifecycle` | The incident phase the item responds to, such as `Failure / Inception` or `Response / ...`. |
| `sts` | The socio-technical layer the item targets, such as `Tech / Core` or `Process / ...`. |
| `intended-effect` | The quality characteristic the item aims to improve. |
| `google-ai` | The goal category, from practitioner guidance on postmortem action items: `prevent`, `detect`, `mitigate future`, and others such as `investigate` and `repair`. Text after `#` is a coder's note. |

Fields coded for this paper:

| Field | Meaning |
|---|---|
| `action-type` | Whether the item evolves the system and, if so, how. See `action-type-coding-guide.md`. Values include `evo / add`, `evo / alter / strengthen`, `evo / alter / weaken`, `evo / subtract`, and `formative / ...`. An item can have more than one value. |
| `matrix-influence` | The risk factor the item acts on: `likelihood` or `consequence`. `unspecified` and `unrelated` mark items outside the matrix. |
| `matrix-approach` | The polarity: `capability` (add or strengthen) or `vulnerability` (remove or weaken). `unspecified` and `unrelated` mark items outside the matrix. |

### How the matrix fields were derived

- **Risk factor** (`matrix-influence`) comes from the goal category. Items aimed at prevention act on likelihood, and items aimed at mitigation act on consequence. Items aimed at detection were assigned case by case, by whether the lead time the detection creates would let a team prevent an incident (`detect / prevent`, likelihood) or mitigate it faster (`detect / mitigate`, consequence).
- **Polarity** (`matrix-approach`) comes from the action type. `evo / add` and `evo / alter / strengthen` give `capability`, and `evo / alter / weaken` and `evo / subtract` give `vulnerability`. An item with both a formative and an evolutionary part is placed by its evolutionary part. Items that are only formative fall outside the matrix.

### Quadrants

| Quadrant | `matrix-influence` | `matrix-approach` | Action items |
|---|---|---|---|
| A: reduce a susceptibility | likelihood | vulnerability | 68 |
| B: add a barrier | likelihood | capability | 101 |
| C: remove an amplifier | consequence | vulnerability | 56 |
| D: add recovery | consequence | capability | 126 |
| Outside the matrix | `unspecified` or `unrelated` | | 11 |
| **Total** | | | **362** |

These counts match the paper's quadrant table. A report's evolutionary strategy is the set of quadrants its action items occupy, and counting reports by that set reproduces the paper's strategy figure.
