# eService-Scheduler

An example project of using eService with Salesforce Scheduler.

## Object Model
View the [ERD](/docs/ERD.drawio.svg) to see an example of how to join Salesforce Scheduler with eService objects. This is only meant as a demonstration and any actual implementation will depend on use case.

## Setup

### Create a User
- ⚙️ -> Setup -> Users -> New User
    - User License: Salesforce Platform
    - Profile: Standard Playform User
    - Enter remaining required user details

### Permission Set License Assignment
From the created User's record (NOT the admin User's record):
- Permission Set License Assignment -> Edit Assignments -> Tick "Salesforce Scheduler" -> Save

### Permission Set Assignment
From the created User's record (NOT the admin User's record):
- Permission Set Assignment -> Edit Assignments -> Assign "eService Permissions" and "eService Scheduler" -> Save

### Salesforce Scheduler Setup
- 𓃑 App Menu -> "Salesforce Scheduler Setup"
- Complete the following steps in the Salesforce Scheduler Setup Assistant
    - Set Up Operation Hours
    - Set Up a Service Territory
    - Create a Resource
        - Active: ✅
        - User: Created User (NOT the admin User's record)
        - Resource Type: Technician (Must be this value in order to be visible when scheduling!)
    - Assign a Location
    - Create a Topic
    - Assign a Topic (Includes creating Work Type Group)
- Navigate to Created Resource
    - Related tab -> Shifts -> New -> Enter record details -> Save

### Salesforce Scheduler Settings
- ⚙️ -> Setup -> "Salesforce Scheduler Settings"
- Recommended enabled options:
    - Event Management
    - Resource Appointment Sharing

### Salesforce Scheduler Policies
- ⚙️ -> Setup -> "Scheduling Policies" -> Default Appointment Scheduling Policy -> Edit
- Recommended Target & Adjustment Types:
    - Use service territory member’s shift
    - Use service territory’s operating hours with shifts