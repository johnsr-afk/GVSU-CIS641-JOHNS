# Overview
This document serves as the Software Requirements Specification (SRS) for the Cat 6 Routing & Length Estimator application. It defines the complete set of functional and non-functional requirements governing the system's behavior, route calculation algorithms, floor plan parsing, and compliance checking mechanisms.

# Functional Requirements

1. Routing & Length Calculation Feature
   1. FR1: The system shall calculate the total 3D cable run length between a designated start node and drop destination, including both horizontal travel distance and vertical drop or rise.
   2. FR2: The system shall automatically append a configurable slack margin percentage and service loop allowance to the raw path length when computing total cable requirements.

2. Obstacle & Constraint Avoidance Feature
   1. FR3: The system shall detect obstacle layers on the floor plan and reroute the cable path around high-voltage power lines and prohibited routing zones.

3. Standard Compliance & Alerting Feature
   1. FR4: The system shall display a compliance warning message to the user whenever an estimated single cable run length exceeds the 100-meter maximum standard limit for Ethernet runs.

# Non-Functional Requirements

1. System Performance
   1. NFR1: The route calculation algorithm shall generate and display the optimal cable path within 2.0 seconds of the user selecting the destination node on a floor plan.

2. Estimation Accuracy
   1. NFR2: The physical length estimation model shall maintain a scale measurement accuracy within +/- 2% of actual measured field distances when given an accurate pixels-to-feet ratio.

3. Interface & Compatibility
   1. NFR3: The application user interface shall allow a user to complete an end-to-end cable routing estimation in 5 or fewer mouse clicks.
   2. NFR4: The application shall render imported CAD floor plan image formats (PNG, JPEG, SVG) across all major modern web browsers without layout degradation.
