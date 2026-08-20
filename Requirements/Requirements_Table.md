# Requirements Table

## Functional Requirements

| ID | Type | Description | Priority | Acceptance Criteria | Rationale |
|---|---|---|---|---|---|
| FR-001 | Functional | The system shall allow a Resident to enter monthly electricity consumption in kWh, gas consumption, and commute distance in km. | High | Pass: Valid monthly values are accepted and stored. Fail: Invalid, negative, or missing values are rejected. | Monthly consumption data is required to calculate the household carbon footprint. |
| FR-002 | Functional | The system shall calculate the household's monthly CO₂-equivalent emissions from recorded electricity, gas, and transport data using configured emission conversion factors. | High | Pass: Calculated emissions are displayed and stored. Fail: Invalid emissions are generated. | Calculating emissions is the main purpose of the system. |
| FR-003 | Functional | The system shall allow a Resident to view historical monthly carbon emissions and compare them across different months. | High | Pass: Previous monthly records and calculated emissions are displayed correctly. Fail: Missing or incorrect records are displayed. | Historical comparison helps residents understand emission trends. |
| FR-004 | Functional | The system shall allow a Resident to set and track a carbon-reduction target and display progress toward the target. | High | Pass: A valid target is stored and progress is updated with new data. Fail: Invalid targets are rejected. | The system must help households track reduction milestones. |
| FR-005 | Functional | The system shall allow a Sustainability Coach to review a household's carbon-emission history and reduction progress. | Medium | Pass: The coach can view emissions, trends, targets, and milestone progress. Fail: Unauthorized users cannot access household information. | Coaches need household progress information to provide sustainability guidance. |

## Non-Functional Requirements

| ID | Type | Description | Priority | Acceptance Criteria | Rationale |
|---|---|---|---|---|---|
| NFR-001 | Performance & Security | The annual carbon-reduction milestone chart shall render interactive historical comparison graphs in under 200 ms while maintaining required security standards under simulated peak load. | High | Pass: Chart rendering is below 200 ms and security standards are maintained during peak-load testing. Fail: Rendering exceeds 200 ms or security requirements are violated. | Fast and secure visualization is necessary for effective system use. |
| NFR-002 | Usability & Reliability | The system shall provide clear input validation and understandable error messages while preserving successfully recorded household data during normal operation. | High | Pass: Users receive clear messages for invalid input and valid records remain available. Fail: Errors are unclear or valid records are lost. | Residents should be able to enter monthly data easily and trust that their records are retained. |
