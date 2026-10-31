# Action Type Coding Guide

This guide describes how we coded the *action type* of each action item in the proposed change dataset. Action type gives the polarity axis of the Evolutionary Response Matrix: whether a change adds or strengthens a capability, or removes or weakens a vulnerability. The risk factor axis (likelihood or consequence) comes from an existing goal category, described in the paper's Methodology section and in `README.md`.

Two researchers developed this guide on a subset of the dataset, applied it independently to a second subset, and discussed disagreements until they were regularly in agreement. One author then coded the remaining action items, discussing uncertain cases when necessary. The guide below is the version the coders worked from, with the list of codes and how they map to the matrix added from the dataset.

## 1. The four categories we are interested in

Keep the high-level categories in mind while coding:

| Quadrant | Category |
|---|---|
| A | **Remove or weaken a susceptibility**, making some kinds of future failures less likely. |
| B | **Add or strengthen a barrier** intended to protect the system from future failures. |
| C | **Remove or weaken an amplifier** that otherwise would exacerbate future failures. |
| D | **Add or strengthen a mitigation** that may reduce the consequence of future failure. |

Action type decides the column (add or strengthen vs. remove or weaken). The risk factor decides the row (likelihood vs. consequence).

## 2. Key questions for action type

- Is the change **more helpful** (add or strengthen) or **less harmful** (subtract or weaken)?
- Are we **fixing a defect** or generally **removing an issue**? If so, subtract or weaken.
- Was there a **property that made things worse** that we are removing? If so, subtract or weaken.
- Does the incident report **word it as adding something or eliminating something**?

## 3. Codes

An action item is coded as evolutionary (`evo`) if it makes a lasting change to the socio-technical system (people, processes, tools, or technology), and as `formative` if it only produces knowledge or agreement for the current plan.

| Code | Meaning | Matrix polarity |
|---|---|---|
| `evo / add` | Adds a capability that did not exist. | Capability (B or D) |
| `evo / alter / strengthen` | Makes an existing capability stronger or more sophisticated. | Capability (B or D) |
| `evo / alter / weaken` | Weakens or constrains an existing part of the system that is a vulnerability. | Vulnerability (A or C) |
| `evo / subtract` | Removes a vulnerability, such as a defect or a harmful property. | Vulnerability (A or C) |
| `formative / ...` | Produces knowledge or agreement only, for example `formative / investigative`, `formative / check`, `formative / discover options`, `formative / consider options`, `formative / schedule`, or `formative / other`. | Outside the matrix |

When an action item has both a formative part and an evolutionary part (for example, investigate and then fix), it is placed in the matrix by its evolutionary part. Items with only formative parts fall outside the matrix.

## 4. Worked examples (IR-14)

IR-14 has good examples for comparing perspectives.

**14.1**
- action: Consider more variables when estimating TTR
- goal: Set more accurate TTR expectations during incident
- action-type: `evo / alter / strengthen`
- Justification: The estimation process exists (therefore not `evo / add`), but we are making it more sophisticated (`evo / alter / strengthen`).

**14.2**
- action: Adjust configuration defining allowed topologies
- goal: Prevent promotion of cross-region DB primaries
- action-type: `evo / alter / weaken`
- Justification: Fix the configuration issue, removing the possibility of a particular topology. This vulnerability was removed.

**14.3**
- action: Accelerate on going migration (replacing mechanism)
- goal: Communicate per service status during incidents
- action-type: `evo / alter / strengthen`
- Justification: Status reporting exists (therefore not `evo / add`), but making it more fine-grained is strengthening the communication capability.

**14.4**
- action: Rearchitect as "well-connected sites in a geography"
- goal: Tolerate single data center failure with no user impact
- action-type: `evo / add` (`evo / alter / strengthen` would probably be fine too)
- Justification: The incident report words this as adding a tolerance capability (reading between the lines).

Example 14.4 shows a boundary case. Adding and strengthening both place an item on the capability side, so the choice between them does not change its quadrant.
