# 🧭 Feature Request Completeness & Open-Coding Guide

A practical taxonomy, workflow, and templates to **identify & code incomplete information** in feature requests. This version adds **parent/child (“part-of”) relationships** between codes and clarifies **who owns what** (Requester vs. Developer).

---

## Table of Contents
- [Why this exists](#why-this-exists)
- [Method: First Batch Open Coding (5 requests)](#method-first-batch-open-coding-5-requests)
- [Identified Codes (with roles)](#identified-codes-with-roles)
- [Codebook & Definitions](#codebook--definitions)
- [Hierarchy: Part-of / Parent–Child](#hierarchy-partof--parentchild)
- [How to Code a Request](#how-to-code-a-request)
- [Quick Completeness Checklist](#quick-completeness-checklist)
- [Issue Template (drop-in)](#issue-template-drop-in)
- [JSON Structure (nested; supports “part_of”)](#json-structure-nested-supports-part_of)
- [Mini Example](#mini-example)
- [Contributing](#contributing)
- [License](#license)

---

## Why this exists

Incomplete feature requests slow teams down, create back-and-forth, and introduce avoidable risk late in delivery.  
This repo provides a **shared vocabulary**, **open-coding workflow**, and **ready-to-use templates** to spot and fill gaps early.

---

## Method: First Batch Open Coding (5 requests)

1. **Open code the first 5 requests.**  
   Each author independently reviews the request and highlights **incomplete information**.

2. **Dual independent coding.**  
   Both authors read the identified gaps and map each gap to one or more **coding categories**.

3. **Convergence meeting.**  
   Authors meet to discuss codes, resolve differences, and agree on a **common code set** for future requests.

4. **Resulting shared code set (Step 1 outcome).**  
   The following codes were identified and refined as a common, reusable set (see roles & hierarchy below).

---

## Identified Codes (with roles)

- **UI/UX components** *(Requester)*
- **Justification** *(Requester)*
- **Goal**
- **Behavior**
- **End User**
- **Time Constraints**
- **Implementation** *(Developer)*
- **Dependency**
- **Configuration**
- **Data Transmission**
- **Security**
- **Testing** *(Developer)*
- **Data/Storage** *(Developer)*

> **Note:** Roles indicate the **primary source of truth** (who typically supplies the information), not exclusive ownership. Many items are collaborative.

---

## Codebook & Definitions

> Use these when tagging incomplete information in requests.

### UI/UX components *(Requester)*
Incomplete or missing **design details** on how the feature appears/behaves in the interface.  
*Example:* “Details on how the setting should be presented in the UI.”

### Justification *(Requester)*
Missing **rationale**: goal, intent, problem statement, expected outcomes.  
*Example:* Why this matters now; success criteria.

### Goal
Missing clear **purpose/objective**.  
*Example:* “Clear purpose or goal of the feature request.”

### Behavior
Missing **decision points/rules** governing how the feature works.  
*Examples:*  
- Global vs. per-conversation scope  
- Show sent time for all vs. some message types  
- Specific functionality expected for emoji feature

### End User
Missing **target audience** or impacted users.  
*Examples:* Benefiting user group, intended personas.

### Time Constraints
Missing **priority, importance, or timeline**.  
*Examples:* Priority level, deadline/milestone, urgency.

### Implementation *(Developer)*
Missing **technical direction** or build details.

### Dependency
Missing details on **requirements/constraints/related artifacts**.  
*Examples:* Platform/environment; related features; how out-of-country is determined (e.g., number country code vs. tower registry); method of sharing (email, social).

### Configuration
Missing **settings/operational parameters**.  
*Examples:*  
- Automatic change vs. sub-setting of SMS fallback  
- What should an invite link do/point to?  
- Extent of invite message customization  
- Applies to incoming MMS, outgoing MMS, or both (same vs. separate settings)

### Security
Missing **security/privacy/safety/permissions** info.  
*Examples:* Required permissions; security & privacy considerations.

### Data Transmission
Missing **data-flow** details.  
*Example:* Should messages be screened server-side before transmission?

### Testing *(Developer)*
Missing **verification plan and impacts** on existing components.  
*Examples:* Potential impacts on send/receive flows; compatibility risks; analytics/tracking requirements.

### Data/Storage *(Developer)*
Missing **data & storage** details.  
*Examples:* Size values; desired max MMS size; expected ranges/limits.

---

## Hierarchy: Part-of / Parent–Child

Some codes are conceptually **part of** others. Use this hierarchy to avoid duplication and to reflect structural relationships when coding.

- **Product Requirements**
  - **Justification** *(parent)* → may include **Goal**
  - **Goal** *(child of Justification)*  
  - **End User** *(sibling to Goal)*  
  - **Time Constraints** *(sibling to Goal)*

- **Functional Design**
  - **Behavior** *(parent)*  
    - **Configuration** *(child of Behavior)*  
    - **UI/UX components** *(child of Behavior)*

- **Technical Delivery**
  - **Implementation** *(parent)*  
    - **Dependency** *(child of Implementation)*  
    - **Data Transmission** *(child of Implementation)*  
    - **Security** *(child of Implementation; also cross-cutting)*  
    - **Data/Storage** *(child of Implementation)*  
    - **Testing** *(child of Implementation)*

> **Guidance:**  
> - If a gap clearly fits a **child** code (e.g., *Configuration*), tag it there.  
> - If it’s broad or spans multiple children, tag the **parent** (e.g., *Behavior* or *Implementation*) and optionally add specific children as secondary tags.  
> - Security can be both a **child of Implementation** and a **cross-cutting** concern—use in both roles when helpful.

---

## How to Code a Request

1. **Highlight gaps** (missing, ambiguous, or conflicting info).  
2. **Assign codes** using the **most specific child** available.  
3. If a gap spans multiple children, **multi-tag** and include the **parent**.  
4. **Note the role** (Requester/Developer) when you need to follow up.  
5. **Record decisions** made during convergence so future requests can reuse them.

---

## Quick Completeness Checklist

```markdown
### Completeness Checklist (with hierarchy cues)

- [ ] PRODUCT REQUIREMENTS
  - [ ] Justification (includes Goal & success criteria)
    - [ ] Goal (one-sentence purpose; “done” looks like…)
  - [ ] End User (personas, accessibility, environments)
  - [ ] Time Constraints (priority, milestone, deadline)

- [ ] FUNCTIONAL DESIGN
  - [ ] Behavior (rules, edge cases, scope)
    - [ ] Configuration (settings, defaults, per-scope overrides)
    - [ ] UI/UX components (screens, states, a11y, responsive)

- [ ] TECHNICAL DELIVERY
  - [ ] Implementation (systems/APIs, migrations, flags, telemetry)
    - [ ] Dependency (related features, envs, external services)
    - [ ] Data Transmission (flows, screening/validation, sync/async)
    - [ ] Security (permissions, privacy, data classification)
    - [ ] Data/Storage (size limits, retention, backups)
    - [ ] Testing (unit/integration/e2e; analytics & dashboards)
