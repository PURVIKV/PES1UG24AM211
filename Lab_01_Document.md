# Lab 1 — Requirements Engineering & UML Use-Case Modelling

## Problem Statement

### Household Carbon Footprint & Target Tracker

A green-living analytics tool where households log monthly utility consumption, including electricity (kWh), gas, and commute distance (km), to compute CO₂-equivalent emissions and track reduction milestones.

**Target Stakeholders / Actors:**

* Resident
* Sustainability Coach

---

# 1. Actors

## 1.1 Primary Actor

### Resident

The Resident is the primary actor who interacts with the system to:

* Enter monthly electricity consumption.
* Enter monthly gas consumption.
* Enter monthly commute distance.
* View calculated carbon emissions.
* View historical emission records.
* Set carbon-reduction targets.
* Track progress toward reduction milestones.

## 1.2 Secondary Actor

### Sustainability Coach

The Sustainability Coach is the secondary actor who reviews household carbon-emission information and reduction progress to provide sustainability guidance.

---

# 2. Functional Requirements

| ID         | Type       | Description                                                                                                                                                                      | Priority | Acceptance Criteria                                                                                                                                       | Rationale                                                                          |
| ---------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **FR-001** | Functional | The system shall allow a Resident to enter monthly electricity consumption in kWh, gas consumption, and commute distance in km.                                                  | High     | **Pass:** Valid monthly values are accepted and stored. **Fail:** Invalid, negative, or missing values are rejected with an error message.                | Monthly consumption data is required to calculate the household carbon footprint.  |
| **FR-002** | Functional | The system shall calculate the household's monthly CO₂-equivalent emissions from the recorded electricity, gas, and transport data using configured emission conversion factors. | High     | **Pass:** Calculated emissions are displayed and stored. **Fail:** Invalid or negative emission values are generated.                                     | Calculating emissions is the main purpose of the system.                           |
| **FR-003** | Functional | The system shall allow a Resident to view historical monthly carbon emissions and compare them across different months.                                                          | High     | **Pass:** Previous monthly records and calculated emissions are displayed correctly. **Fail:** Missing or incorrect historical records are not displayed. | Historical comparison helps residents understand their emission trends.            |
| **FR-004** | Functional | The system shall allow a Resident to set and track a carbon-reduction target and display progress toward the target.                                                             | High     | **Pass:** A valid target is stored and progress is updated when new monthly data is recorded. **Fail:** Invalid targets are rejected.                     | The system must help households track carbon-reduction milestones.                 |
| **FR-005** | Functional | The system shall allow a Sustainability Coach to review a household's carbon-emission history and reduction progress.                                                            | Medium   | **Pass:** The coach can view emissions, trends, targets, and milestone progress. **Fail:** Unauthorized users cannot access household information.        | The coach needs household progress information to provide sustainability guidance. |

---

# 3. Non-Functional Requirements

| ID          | Type                    | Description                                                                                                                                                                                    | Priority | Acceptance Criteria                                                                                                                                                                                    | Rationale                                                                                        |
| ----------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| **NFR-001** | Performance & Security  | The annual carbon-reduction milestone chart shall render interactive historical comparison graphs in under **200 ms** while maintaining required security standards under simulated peak load. | High     | **Pass:** Benchmarking confirms chart rendering under 200 ms and security standards are maintained during peak-load testing. **Fail:** Rendering exceeds 200 ms or security requirements are violated. | Fast and secure visualization is necessary for effective and safe use of the system.             |
| **NFR-002** | Usability & Reliability | The system shall provide clear input validation and understandable error messages while preserving successfully recorded household data during normal operation.                               | High     | **Pass:** Users receive clear messages for invalid input and successfully submitted records remain available. **Fail:** Errors are unclear or valid records are lost.                                  | Residents should be able to enter monthly data easily and trust that their records are retained. |

---

# 4. UML Use-Case Diagram

The UML Use-Case Diagram contains the following actors and use cases.

## Actors

* **Resident** — Primary Actor
* **Sustainability Coach** — Secondary Actor

## Primary Use Cases

1. Enter Monthly Consumption
2. Calculate Carbon Footprint
3. View Emission History
4. Set Reduction Target
5. Track Reduction Progress
6. Review Household Progress
7. Generate Milestone Notification

## UML Relationships

### `<<include>>`

**Enter Monthly Consumption** `<<include>>` **Calculate Carbon Footprint**

This means that calculating the carbon footprint is a required part of processing the entered monthly consumption data.

**Track Reduction Progress** `<<include>>` **Calculate Carbon Footprint**

This allows the system to use the calculated carbon footprint when updating reduction progress.

**Review Household Progress** `<<include>>` **View Emission History**

This allows the Sustainability Coach to use the household's historical emission information while reviewing progress.

**Review Household Progress** `<<include>>` **Track Reduction Progress**

This allows the Sustainability Coach to review the household's reduction progress.

### `<<extend>>`

**Generate Milestone Notification** `<<extend>>` **Track Reduction Progress**

The milestone notification is conditional and occurs when the household reaches a relevant carbon-reduction milestone.

---

# 5. Actor–Use Case Relationships

| Actor                | Use Case                  |
| -------------------- | ------------------------- |
| Resident             | Enter Monthly Consumption |
| Resident             | View Emission History     |
| Resident             | Set Reduction Target      |
| Resident             | Track Reduction Progress  |
| Sustainability Coach | Review Household Progress |

---

# 6. Use-Case Flow Specification

## UC-01: Log Monthly Consumption and Calculate Carbon Footprint

### Primary Actor

Resident

### Supporting Actor

System

### Goal

Allow the Resident to enter monthly household consumption data and obtain the corresponding CO₂-equivalent emissions.

---

## 6.1 Preconditions

1. The Resident has access to the system.
2. A household profile exists.
3. Required emission conversion factors are available in the system.
4. The Resident has the monthly electricity, gas, and commute data.

---

## 6.2 Postconditions

### Success

1. Monthly electricity, gas, and commute data are stored.
2. The system calculates the household's CO₂-equivalent emissions.
3. The calculated emissions are associated with the corresponding month.
4. The updated information can be used for historical comparison and reduction tracking.

### Failure

1. Invalid data is not stored.
2. The system displays an appropriate error message.
3. The Resident can correct the input and try again.

---

# 7. Main Success Scenario

| Step   | Actor    | Action                                                                              |
| ------ | -------- | ----------------------------------------------------------------------------------- |
| **1**  | Resident | Opens the monthly consumption entry screen.                                         |
| **2**  | System   | Displays fields for electricity consumption, gas consumption, and commute distance. |
| **3**  | Resident | Enters the monthly electricity consumption in kWh.                                  |
| **4**  | Resident | Enters the monthly gas consumption.                                                 |
| **5**  | Resident | Enters the monthly commute distance in km.                                          |
| **6**  | Resident | Submits the monthly consumption data.                                               |
| **7**  | System   | Validates the entered values.                                                       |
| **8**  | System   | Applies the configured emission conversion factors.                                 |
| **9**  | System   | Calculates the total CO₂-equivalent emissions.                                      |
| **10** | System   | Stores the monthly consumption and calculated emissions.                            |
| **11** | System   | Displays the calculated carbon footprint to the Resident.                           |
| **12** | System   | Updates historical emission and reduction-progress information.                     |

---

# 8. Alternate Flow

## AF-01: Invalid Monthly Consumption Data

**At Step 7 of the Main Success Scenario:**

1. The system detects that one or more entered values are invalid.
2. The system does not save the invalid record.
3. The system displays an appropriate error message.
4. The Resident corrects the entered values.
5. The system validates the corrected values.
6. If the values are valid, the system continues from **Step 8** of the Main Success Scenario.

---

# 9. Summary

The Household Carbon Footprint & Target Tracker allows residents to record monthly electricity, gas, and commute information, calculate CO₂-equivalent emissions, view historical emissions, set reduction targets, and track progress.

The Sustainability Coach can review household emission history and reduction progress.

The UML model includes both `<<include>>` and `<<extend>>` relationships to represent required and conditional system behavior.
