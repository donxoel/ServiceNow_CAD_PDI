Loaner Request Application 🚗💻
ServiceNow CAD Certification PDI Project
Overview
The Loaner Request application is a custom ServiceNow scoped application designed to manage the end-to-end lifecycle of short-term asset loans (such as laptops, tablets, or vehicles). This project was developed as part of the ServiceNow Certified Application Developer (CAD) learning path to demonstrate proficiency in building custom applications on the Now Platform.

🛠 Key Features
Self-Service Portal: Users can submit requests for specific equipment with start and end dates.

Automated State Management: Tracks the transition from Requested to Reserved, Deployed, and Returned.

Dynamic Validations: Ensures end dates are not before start dates and prevents weekend pickups via Client Scripts.

Automated Notifications: Sends alerts to users when their loaner item is ready for pickup or overdue.

Reporting & Dashboards: Visualizes current loaner trends and inventory availability.

🏗 Technical Components
1. Data Model
Table: x_snc_loaner_req_loaner_request (Extends Task)

Key Fields:

Item Type: Choice list (Laptop, Mobile, Other).

Start Date / End Date: Date/Time fields for duration.

Depot: Reference to location records.

2. Business Logic & Scripting
Client Scripts: UI validation for date consistency and "Requested for" auto-population.

Business Rules: Server-side logic to calculate duration and handle state transitions.

Script Includes: Reusable AJAX calls for date calculations using GlideDateTime.

3. Workflow & Automation
Flow Designer: Handles approval routing and task creation for the fulfillment team.

Scheduled Jobs: Daily checks to identify overdue items and trigger "Long-term Loan" reminders.

4. Security
ACLs: Role-based access control for admin, user, and fulfiller roles.

Application Scoping: Ensures the application logic is isolated and does not conflict with Global scope apps.

🚀 Installation & Setup
Fork this repository.

In your ServiceNow PDI, navigate to Studio.

Select Import from Source Control.

Paste your Repository URL and Credentials.

Run the Scheduled Script Execution "Generate Mock Data" (if included) to populate your instance.

📸 Preview
Tip: Take a screenshot of your Loaner Request Form or Dashboard and save it as screenshot.png in your repo to display it here!
