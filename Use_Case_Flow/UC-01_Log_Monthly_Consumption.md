# UC-01: Log Monthly Consumption and Calculate Carbon Footprint

## Primary Actor

Resident

## Supporting Actor

System

## Goal

Allow the Resident to enter monthly household consumption data and obtain the corresponding CO₂-equivalent emissions.

## Preconditions

1. The Resident has access to the system.
2. A household profile exists.
3. Required emission conversion factors are available.
4. The Resident has the monthly electricity, gas, and commute data.

## Postconditions

### Success

1. Monthly electricity, gas, and commute data are stored.
2. The system calculates the household's CO₂-equivalent emissions.
3. The calculated emissions are associated with the corresponding month.
4. The information can be used for historical comparison and reduction tracking.

### Failure

1. Invalid data is not stored.
2. The system displays an appropriate error message.
3. The Resident can correct the input and try again.

## Main Success Scenario

| Step | Actor | Action |
|---|---|---|
| 1 | Resident | Opens the monthly consumption entry screen. |
| 2 | System | Displays fields for electricity consumption, gas consumption, and commute distance. |
| 3 | Resident | Enters monthly electricity consumption in kWh. |
| 4 | Resident | Enters gas consumption. |
| 5 | Resident | Enters monthly commute distance in km. |
| 6 | Resident | Submits the monthly consumption data. |
| 7 | System | Validates the entered values. |
| 8 | System | Applies the configured emission conversion factors. |
| 9 | System | Calculates total CO₂-equivalent emissions. |
| 10 | System | Stores the monthly consumption and calculated emissions. |
| 11 | System | Displays the calculated carbon footprint to the Resident. |
| 12 | System | Updates historical emission and reduction-progress information. |

## Alternate Flow

### AF-01: Invalid Monthly Consumption Data

At Step 7:

1. The system detects that one or more entered values are invalid.
2. The system does not save the invalid record.
3. The system displays an appropriate error message.
4. The Resident corrects the values.
5. The system validates the corrected values.
6. If the values are valid, the system continues from Step 8 of the Main Success Scenario.
