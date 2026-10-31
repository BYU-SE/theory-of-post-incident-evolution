# Practitioner Interviews: Protocol, Codebook, and Quotes

This document describes the practitioner interviews used in the paper. It has three parts: the interview protocol, the codebook that connects our codes to the theory, and a table that links each interview quote in the paper to its interview.

We do not share the interview transcripts. Seven of the nine interviews were collected for a prior study of learning from incidents, and their transcripts were not published there. The participants agreed to take part under an approved Institutional Review Board protocol, and the transcripts contain details that could identify participants and their organizations even after names are removed.

## 1. Interview Protocol

### 1.1 Participants

We analyzed nine interviews with practitioners who have experience with incident analysis, incident response, and selecting and carrying out the changes that follow. Participants come from organizations that vary in size and domain, and they hold different roles in those organizations, as described in the paper.

I1 through I7 were collected for the prior study, the interviews were semi-structured and open-ended beginning with a general prompt, which was described in the research paper these interviews came from.

I8 and I9 were conducted for this work and followed the same protocol (Section 1.2), with the addition of a partial member check (Section 1.3).

### 1.2 Open-Ended Portion

The interviews were semi-structured and open-ended. Each began with a general prompt such as:

> We are interested in how you learn and evolve from incidents; we would love to hear anything you can tell us.

We asked participants to ground the conversation in specific incidents they had been part of, and in the action items that followed, rather than speak only in general terms. By an incident we meant an outage, degradation, or other event that led to some form of post-incident analysis.

The interviewer then followed the participant's account. Follow-up questions explored how changes are proposed, prioritized, negotiated, and carried out after an incident. Typical follow-ups included:

- What happened in the weeks after the incident? Did any actions or changes come out of it?
- What guided the selection of those action items? Why was one item chosen over another?
- Were there constraints on what you could reasonably propose?
- What distinguished the action items that got done from the ones that did not?
- Who decided what would be done, and how was the work prioritized against other work?
- What happened to the action items over time?
- Does your team or organization have a philosophy about why it takes action after an incident?

### 1.3 Partial Member Check

After the open-ended portion, the interviewer presented preliminary ideas from our analysis and asked the participant to respond: whether the ideas matched their experience, what nuance they would add, and whether other ideas were missing. The ideas presented were:

- **Dimensions of generalization.** Ways that teams look beyond the specific incident when they write action items: the condition that caused the failure (such as a similar bug or trigger), the locality where the same problem could appear (other services, data centers, or parts of the codebase), and anticipation of how a condition could worsen with growth or trends. In I9 we also presented generalization by impact on customers and by time (such as a seasonal load peak).
- **Relationships among the action items in a plan** (I9). Preliminary patterns in how the items of one plan relate to each other, for example fixing a defect and then hardening the surrounding system, stacking several independent protections against the same failure, and pairing a quick temporary change with a later durable fix.

Some of these ideas carried into the theory, including generalization, anticipation, and aspects of tolerable risk. Others changed substantially as we refined the theory and reframed it around the Evolutionary Response Matrix. Because the member check presented our own ideas, and sometimes used leading questions, we treated a participant's agreement during this portion as weaker evidence than what they offered in the open-ended portion.

## 2. Codebook

We analyzed the transcripts using constructivist grounded theory. We began with initial open coding of all nine transcripts, developed focused codes, and returned to the transcripts to apply and extend those codes, writing memos and comparing incidents and codes throughout. Recurring focused codes were raised into the categories that became the theory.

The codebook below gives the final categories and focused codes as they appear in the paper. For each code it gives a definition and the interviews that the paper draws on for it. Quote numbers (Q1, Q2, ...) refer to the table in Section 3.

### 2.1 Strategic Adaptation (Paper Section "Strategic Adaptation")

A strategic adaptation is a change to a team's proposed strategy (the action items in its incident report), made as the work is carried out. The proposed strategy and the realized strategy (the changes ultimately completed) may differ in important ways.

**Types of adaptation.** The three types come from a prior study of post-incident changes at one organization, which served as a sensitizing concept for our analysis of the interviews.

| Type | Definition |
|------|------------|
| Scope change | An item is narrowed, expanded, split into smaller tasks, or replaced. Work on an item may continue to decide what change to make, so its scope can still change after the plan is written. |
| Timing change | An item is completed earlier or later than originally planned. |
| Abandonment and loss | An item is abandoned when someone explicitly stops it, for example by closing an incomplete task. It is lost when it is forgotten in the backlog or never recorded as a task. |

**Tensions that make adaptation more likely.** These codes come from the interviews. A proposed strategy reflects a judgment made at one point in time, and each tension challenges and tests that judgment.

| Code | Definition | Resulting adaptation | Interviews | Quotes |
|------|------------|----------------------|------------|--------|
| Estimating cost and effort | The effort an item needs may not be well understood until work on it begins. If it needs much more effort than expected, its scope may be adapted. | Scope change | I9 | Q1, Q2 |
| Competing with other work | Post-incident items must be prioritized against other planned work and against items from other incidents. Some are urgently prioritized, and others languish. | Timing change | I4, I6, I8 | Q3 |
| Changing perceptions of risk | The risk a team perceives in an item can change over time. A recurrence can make a planned item more urgent, and a stopgap can become permanent while the item with the durable fix is delayed or abandoned. | Timing change; abandonment | I9 | Q4 |
| Sustaining coordinated work | Large, long-term, or cross-team items need coordinated work sustained over months or years. Changes to team membership, business funding, or team structure can lead to such items being abandoned or lost without any explicit decision. | Abandonment and loss | I2, I4, I9 | |

### 2.2 Tolerable Risk (Paper Section "Decision Making and Tolerable Risk")

Tolerable risk is the "level of risk that is accepted in a given context based on the current values of society" (ISO/IEC Guide 51). We found that it rests on two judgments: how much risk is present in a system, and how much of it is tolerable. Both judgments are socially constructed and contextual, and both are dynamic. We identified eight influences on these judgments.

**Risk in decisions.** Evidence that teams make post-incident decisions in terms of risk.

| Code | Definition | Interviews | Quotes |
|------|------------|------------|--------|
| Decisions framed by risk | Whether to halt other work and fix something at once depends on the consequence of the incident and how likely it is to repeat. | I6 | |
| Resources follow risk | Most post-incident work has to fit in the time a team already has, but teams make room for work when a risk is judged high enough, and leave it in normal planning when it is not. The same organization can decide either way. | I5, I6 | Q5 to Q7 |
| Stopping short | Teams stop short of removing all of the risk: they ask how well a problem needs to be solved, and may do nothing when reducing a risk would cost more than keeping it. | I1, I5 | Q8 |

**Judging how much risk is present.** This judgment has two parts: *generalization*, how far a team looks beyond the instance it encountered to the broader class it belongs to, and *anticipation*, how far it looks ahead to failures that have not happened yet.

| Code | Property | Definition | Interviews | Quotes |
|------|----------|------------|------------|--------|
| Experience level of team members | Socially constructed | People with different experience see different risks in the same incident. In generalization, junior engineers tend to stay with the one incident while senior engineers dig deeper. In anticipation, experienced reviewers spot problems that tend to occur together, and teams bring in others' experience through practices such as curating near misses. | I2, I3, I4, I6 | Q9, Q10 |
| Little feedback on what works | Socially constructed | Teams can rarely confirm whether a past change prevented a failure. When a team cannot find the cause of a failure, adding a guard may be the only option, since reducing a susceptibility requires knowing where it is. | I3, I9 | Q11 to Q13 |
| Stakes of the failure | Contextual | The same failure can carry a different risk depending on when it happens, who it affects, and what an organization values. | I6, I7, I8 | Q14 to Q17 |

**Judging how much risk is tolerable.**

| Code | Property | Definition | Interviews | Quotes |
|------|----------|------------|------------|--------|
| Roles, ownership, and authority | Socially constructed | People in different roles judge the same risk differently, and the people with authority decide. Authority can also make room for work. Broad and cross-team work often has no one who both owns it and can set other work aside for it. | I2, I5 | Q18 to Q20 |
| Control over the cause | Contextual | When the cause sits in a vendor's or another team's system, reducing the susceptibility is not an option, and the team works on its own side instead. | I3 | Q21 |
| Cost and capacity | Contextual | Every change has a cost and a risk of its own, weighed against the risk it removes. Removal can carry a regression risk, and addition carries a lasting cost. Teams also weigh a change against what they can do at once. | I1, I7 | Q22, Q23 |

**Both judgments are dynamic.** Teams make both judgments repeatedly, because the context changes: the people involved change, the system changes, and other post-incident changes are completed or set aside.

| Code | Judgment | Definition | Interviews | Quotes |
|------|----------|------------|------------|--------|
| Recurrence | Risk present | A recurrence raises the risk a team sees, and can bring systemic changes a single incident does not. | I1, I7 | Q24, Q25 |
| Time since the incident | Either | As an incident recedes, the risk a team sees may fade or its tolerance may rise; the interviews do not separate the two. A stopgap lowers the risk present and can stall the durable fix. | I9 | Q26 |

### 2.3 Limits of Tolerable Risk (Paper Section "Decision Making and Tolerable Risk")

| Code | Definition | Interviews | Quotes |
|------|------------|------------|--------|
| Risk left without a judgment | Risk that remains not because a team judged it tolerable, but because no one generalized to it or anticipated it, no one could change it, no one made room for the work, or the work waited without anyone weighing the delay. A rule can also stand in for a judgment. | I8 | |

## 3. Interview Quotes in the Paper

Each row in the following table is a quote as it appears in the paper, the interview it comes from, and the topic the participant was discussing. Where the transcript has timestamps, we give the timestamp of the participant's turn. Some transcripts were not timestamped. "[..]" in a quote marks a removed filler word.

| # | Paper section | Interview | Time | Quote | Context in the interview |
|---|---------------|-----------|------|-------|--------------------------|
| Q1 | Adaptation: estimating cost and effort | I9 | | "trying to get it done" | Teams write action items by what would fix the problem, without thinking about how possible they are; reality sets in as they try to do the work. |
| Q2 | Adaptation: estimating cost and effort | I9 | | "reality sets in" | Same turn as Q1. |
| Q3 | Adaptation: competing with other work | I6 | | "worked 16 hour days for two weeks" | A database overload led the team to drop its roadmap and add sharding before a seasonal peak. |
| Q4 | Adaptation: changing perceptions of risk | I9 | | "become your permanent fixes" | Stopgap fixes that remain because the permanent fix is hard to fund. |
| Q5 | Tolerable risk: resources follow risk | I5 | 00:10:48 | "they found resources to help me solve the problem" | An emergency competed with an external commitment; management lent people from teams working on lower-priority items. |
| Q6 | Tolerable risk: resources follow risk | I6 | | "based on our perceived risk" | Same account as Q3: the decision to stop roadmap work and shard the database. The full sentence reads "We had to make that decision based on our perceived risk". |
| Q7 | Tolerable risk: resources follow risk | I6 | 00:37:41 | "not something that we're going to stop everything and go do right now" | Wrapping every database query in the ORM, which went into the next quarter's planning because things were generally working. |
| Q8 | Tolerable risk: stopping short | I5 | 00:48:28 | "how well does the problem really need to be solved?" | Doing the critical items of a plan and weighing the return on investment of the rest. |
| Q9 | Tolerable risk: experience | I6 | 00:20:18 | "the more unobvious questions" | Junior engineers ask surface-level questions during analysis, and senior engineers dig deeper. |
| Q10 | Tolerable risk: experience | I3 | 00:45:59 | "maybe we were lucky this time, but the next time it could be really bad" | Identifying risks from near misses. |
| Q11 | Tolerable risk: little feedback | I9 | | "making things not happen" | How hard it is to measure whether post-incident work helps. |
| Q12 | Tolerable risk: little feedback | I9 | | "it's impossible to know" | Same turn as Q11. |
| Q13 | Tolerable risk: little feedback | I3 | 00:08:45 | "I don't actually understand how this happened, but I'm going to put some extra code in here" | Analyzing an incident where the problem could not always be reproduced or located in the code. |
| Q14 | Tolerable risk: stakes | I7 | 00:24:44 | "out of [..] caution" | Premortems with other engineering teams ahead of the team's busiest period. "[..]" marks a removed "like". |
| Q15 | Tolerable risk: stakes | I6 | | "when there is an incident that is customer facing" | The organization runs a formal postmortem only for incidents with customer impact. |
| Q16 | Tolerable risk: stakes | I8 | | "student obsessed" | The first of the organization's key attributes, that everything it does is for the students. |
| Q17 | Tolerable risk: stakes | I8 | | "even if one student is having a problem, you stop what you are doing and you fix it for that one student" | Same turn as Q16: the organization solves problems for the individual student. |
| Q18 | Tolerable risk: roles | I2 | | "never given the time and space to be done" | Action items that developers, product management, and technical program managers did not prioritize. |
| Q19 | Tolerable risk: roles | I2 | | "a major incident a week" | A period of about eight weeks of repeated major incidents. |
| Q20 | Tolerable risk: roles | I2 | | "the ability to carve out time from the road map" | Same account as Q18: the director asked the business partners for roadmap time to address the incidents, and they agreed. |
| Q21 | Tolerable risk: control | I3 | 00:53:33 | "our UI isn't quite as good, but we don't break" | Taking a dependency that did not treat the team's use as critical out of the team's critical path. |
| Q22 | Tolerable risk: cost and capacity | I1 | | "everything has a cost" | How much an organization is willing to put in place to mitigate a risk; mitigations are expensive to build and difficult to maintain. |
| Q23 | Tolerable risk: cost and capacity | I7 | 00:42:42 | "own less" | Preferring to do better with existing systems than to build new ones. |
| Q24 | Tolerable risk: recurrence | I7 | 00:45:02 | "really, really frequently" | A proper fix would take a quarter of two engineers' time and would not be prioritized otherwise. |
| Q25 | Tolerable risk: recurrence | I1 | | "let's get rid of the Oracle database. That took five years" | Large changes made to prevent issues that kept recurring. |
| Q26 | Tolerable risk: time since | I9 | | "in part because the stopgap fix is there" | Same turn as Q4: the permanent fix is hard to fund while the stopgap is in place. |
