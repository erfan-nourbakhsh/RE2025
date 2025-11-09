# README: Incomplete Information Code Framework

## Overview
This framework identifies and categorizes **incomplete information** within feature requests across two main contributor roles: **Requester** and **Developer**.
Each category includes sub-codes describing the type of missing information, followed by clear definitions and examples.

---

## Identified Codes (after Step 1)

- **UI/UX components** (Requester)
- **Justification** (Requester)
  - Goal
  - Behavior
  - End User
  - Time Constraints
- **Implementation** (Developer)
  - Dependency
  - Configuration
  - Data Transmission
  - Security
- **Testing** (Developer)
- **Data/Storage** (Developer)

---

## Definitions

### UI/UX Components
Incomplete information that relates to **design (UI/UX)** details missing from a feature request.
*Example:* “Details on how the setting should be presented in the user interface.”

---

### Justification
Incomplete information associated with the **goal**, **intent**, and other **requirements** for the feature request.

- **Goal**
  Missing goal or purpose of the feature request.
  *Example:* “Clear purpose or goal of the feature request.”

- **Behavior**
  Missing decision points or functional expectations for the feature request.
  *Examples:*
  “Information on whether this setting should be applied globally or per conversation.”
  “Clarification on whether the sent time should display for all messages or only certain types.”
  “Specific functionality or behavior expected with the emoji feature.”

- **End User**
  Missing information about the **target audience** or **intended user group** impacted by the feature.
  *Examples:* “Target audience or users who will benefit from this feature.”, “Intended user group.”

- **Time Constraints**
  Missing information about **priority**, **importance**, or **timeline** for project management.
  *Examples:* “Priority of the request.”, “Deadline or timeline for implementation.”, “Priority or importance of the feature request.”

---

### Implementation
Incomplete information about **implementation details** in the feature request.

- **Dependency**
  Missing information about dependencies between code and other software components.
  *Examples:*
  “Specific platform or environment where the feature should be implemented.”
  “Any dependencies or related features that should be considered.”
  “Method used to determine when a contact is out-of-country (e.g., phone number or cell-tower data).”
  “Method of sharing (e.g., email, social media).”

- **Configuration**
  Missing information about **settings or configuration** behavior required for operation.
  *Examples:*
  “Should this be an automatic change or an additional sub-setting of SMS fallback?”
  “What should the link itself do or point to — app store page, friend association, or both?”
  “Extent of customization for the invite message.”
  “Does this apply to incoming/outgoing MMS, or both?”

- **Security**
  Missing information regarding **security, privacy, permissions, or access**.
  *Examples:*
  “Specification on user permissions needed to change this setting.”
  “Security and privacy considerations.”

- **Data Transmission**
  Missing information related to **data flow** within the software.
  *Example:* “How should this limitation be implemented? Should messages be screened by the server before transmission?”

---

### Testing
Incomplete information about the **impact** of implementation on the existing system.
This includes unit → integration testing and how the new feature affects other components.
*Examples:*
- “Potential impacts on existing system for sending and receiving messages.”
- “Details on how this change might affect existing functionalities or dependencies.”
- “Potential impact on existing features or compatibility issues.”
- “Analytics or tracking requirements for feature usage.”

---

### Data/Storage
Incomplete information regarding **data handling** or **storage** requirements.
*Examples:*
- “What size values should be provided?”
- “Details about the desired maximum size limit for MMS.”
- “Expected range or limits for the MMS size change.”

---

## Usage Notes
- The hierarchy reflects which **role** (Requester or Developer)** the incomplete information most often originates from.
- Each **definition** serves as a guide for identifying missing elements during qualitative coding or feature-request review.
- Maintain the indentation and order for clarity when coding or referencing in analysis tools.
