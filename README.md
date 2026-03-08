# Loaner Request Application 📋
**ServiceNow Certified Application Developer (CAD) - Training Project**

## 📖 Project Overview
The **Loaner Request** application is a custom scoped application built on the ServiceNow Now Platform. It automates the process of requesting, approving, and tracking short-term assets (Laptops, Mobile Devices, etc.) within an organization.

This project demonstrates core CAD competencies including **Data Modeling**, **UI Customization**, **Server-side Scripting**, and **Flow Automation**.

---

## 🛠 Technical Features

### 1. Data Schema & UI
* **Table:** `x_cdltd_loaner_r_0_loaner_request` (Extends `Task`).
* **Form Design:** Organized using **Sections** (Financials, Logs & Dates, Statistics) and **Annotations** for user guidance.
* **Views:** Created a specific 'Self Service' view for end-users.

### 2. Business Logic (Scripting)
* **Client Scripts:**
    * `Set Start Date`: Automatically sets the start date to Today.
    * `Validate Dates`: Prevents the End Date from being set before the Start Date using `GlideDateTime`.
* **Business Rules:**
    * `Set Duration`: Calculates the total loan time before the record is saved.
    * `Task Updates`: Syncs work notes between the Request and child Tasks.
* **Script Includes:**
   * `LoanerUtils`: A server-side class to handle complex date calculations and availability checks.

### 3. Process Automation
* **Flow Designer:**
    * Trigger: Record Created.
    * Actions: Sends Approval to Manager -> Creates Catalog Tasks for Fulfillment -> Sends Confirmation Email.
* **Scheduled Script Executions:** A daily job that checks for Overdue records and updates the state to 'Missed Return'.

### 4. Security & Access
* **Roles:** Created `x_cdltd_loaner_r_0.admin` and `x_cdltd_loaner_r_0.user`.
* **ACLs:** Restricted the Financials section to only be visible to users with the Admin role.
* **Module Permissions:** Controlled visibility of the Application Menu in the Filter Navigator.

---

## 🚀 How to Use
1. **Submit:** Users navigate to the Loaner Request module and fill out the form.
2. **Approve:** The Requested For's manager receives an approval request.
3. **Deploy:** Once approved, a UI Policy highlights the 'Asset Tag' field for the technician to fill.
4. **Return:** Closing the task triggers a notification to the user thanking them for the return.

---

## 📂 Repository Structure
* `update/`: Contains the XML payloads for application files.
* `dictionary/`: Table and field definitions.
* `sys_script/`: Business Rules and logic.

---
*Developed as part of the ServiceNow CAD Learning Path.*
