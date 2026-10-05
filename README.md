# 🚚 Swift Ship Tracker

## Salesforce-Based Parcel Delivery Management System

Swift Ship Tracker is a scalable **Salesforce CRM solution** designed to simplify and manage the complete parcel delivery lifecycle. The system helps customers book and track parcels, enables delivery agents to update shipment status, provides automated notifications, and gives administrators reports and dashboards for monitoring delivery operations.

The project combines **Salesforce CRM, Flow Automation, Prompt Builder/Agentforce AI, Reports & Dashboards, Experience Cloud, and role-based security** to provide an efficient parcel management platform.

---

# 1. Project Overview

Traditional parcel management systems may require customers and support teams to manually check shipment information. Swift Ship Tracker provides a centralized Salesforce-based solution where parcel information, sender details, receiver details, delivery status, and operational information can be managed from one platform.

### Main Goals

* Simplify parcel booking and management.
* Provide real-time parcel tracking.
* Automate delivery status updates.
* Send notifications when parcel status changes.
* Maintain sender and receiver information.
* Provide AI-assisted parcel tracking.
* Help administrators monitor delivery performance.
* Implement secure role-based access.
* Reduce manual work using Salesforce automation.

---

# 2. Project Scope

The project covers the complete parcel delivery lifecycle:

```text
Parcel Booking
      ↓
Dispatch
      ↓
In Transit
      ↓
Out for Delivery
      ↓
Delivered
      ↓
Delivery Confirmation
```

The system supports customers, delivery agents, customer support teams, administrators, and system developers.

### In Scope

* Customer and sender management
* Receiver management
* Parcel booking
* Parcel tracking
* Delivery status management
* Automated notifications
* AI-based parcel assistance
* Reports and dashboards
* User access management
* Data security
* Salesforce automation

### Out of Scope

* Physical transportation management
* Payment gateway implementation
* Real-world GPS hardware tracking
* Warehouse hardware automation

---

# 3. Project Objectives

The major objectives of Swift Ship Tracker are:

### Objective 1 — Parcel Management

Create a centralized system to store and manage parcel information.

### Objective 2 — Real-Time Tracking

Allow users and support teams to identify the current status of a parcel.

### Objective 3 — Automation

Reduce manual work using Salesforce Flow and automated notifications.

### Objective 4 — AI Assistance

Use Prompt Builder / Agentforce to provide intelligent parcel-status assistance.

### Objective 5 — Operational Monitoring

Provide dashboards and reports for monitoring parcel flow and delivery performance.

### Objective 6 — Security

Protect customer and parcel information using profiles, permission sets, and access controls.

---

# 4. Users Involved

## Customers / Senders

Customers are the primary users of the system.

### Responsibilities

* Book parcels.
* Provide sender details.
* Provide receiver details.
* Track parcel status.
* Receive delivery notifications.
* Ask AI-based tracking questions.

---

## Delivery Agents

Delivery agents manage assigned parcels.

### Responsibilities

* View assigned parcels.
* Update delivery status.
* Confirm delivery.
* Maintain delivery information.
* Ensure timely handover.

### Delivery Status

```text
Booked
   ↓
In Transit
   ↓
Out for Delivery
   ↓
Delivered
```

---

## Customer Support Team

The customer support team handles delivery-related issues.

### Responsibilities

* Respond to customer queries.
* Check parcel information.
* Handle delivery problems.
* Support customers with tracking.
* Communicate delivery information.

---

## Admin Team

Administrators manage the Salesforce environment.

### Responsibilities

* Manage users.
* Configure security.
* Monitor system performance.
* Manage Salesforce configuration.
* Create reports and dashboards.
* Maintain data quality.

---

## System Integrator / Developer

The developer is responsible for implementing and maintaining the technical solution.

### Responsibilities

* Configure Salesforce.
* Create custom objects and fields.
* Build automation.
* Configure Prompt Builder / Agentforce.
* Implement security.
* Test the application.

---

# 5. Gathering & Analysing User Needs

The project requirements were identified based on the activities performed by each type of user.

| User           | Requirement          | Expected Result                      |
| -------------- | -------------------- | ------------------------------------ |
| Customer       | Book parcel          | Parcel record is created             |
| Customer       | Track parcel         | Current status can be viewed         |
| Customer       | Receive updates      | Notifications are received           |
| Delivery Agent | View assigned parcel | Assigned deliveries are accessible   |
| Delivery Agent | Update status        | Parcel status is updated             |
| Support Team   | Handle queries       | Customer issues can be resolved      |
| Admin          | Monitor operations   | Reports and dashboards are available |
| Developer      | Automate processes   | Manual operations are reduced        |

---

# 6. Functional Requirements

## 6.1 Parcel Booking

The system should allow customers or authorized users to create parcel records.

Required information may include:

* Parcel ID
* Sender
* Receiver
* Pickup information
* Delivery information
* Parcel status
* Delivery agent
* Booking date

---

## 6.2 Parcel Tracking

Users should be able to identify the current status of a parcel.

Example:

```text
Parcel ID: SST-1001

Status:
Booked → In Transit → Out for Delivery → Delivered
```

---

## 6.3 Delivery Status Management

Delivery agents should be able to update the parcel status as the shipment progresses.

Supported statuses:

* Booked
* In Transit
* Out for Delivery
* Delivered

---

## 6.4 Automated Notifications

When the parcel status changes, Salesforce automation can trigger notifications.

Example:

```text
Status Changed
      ↓
Salesforce Flow
      ↓
Check New Status
      ↓
Send Notification
      ↓
Customer Receives Update
```

---

## 6.5 Sender and Receiver Management

The system stores information required for parcel communication.

### Sender Information

* Name
* Phone
* Email
* Address

### Receiver Information

* Name
* Phone
* Email
* Address

---

# 7. Salesforce Features and Tools

The project uses multiple Salesforce features.

| Salesforce Tool  | Purpose                        |
| ---------------- | ------------------------------ |
| Custom Objects   | Store parcel and delivery data |
| Custom Fields    | Store required information     |
| Flow Builder     | Automate business processes    |
| Email Alerts     | Send delivery notifications    |
| Prompt Builder   | Create AI prompts              |
| Agentforce       | AI-powered assistance          |
| Experience Cloud | Customer-facing portal         |
| Reports          | Analyse delivery information   |
| Dashboards       | Visualize performance          |
| Profiles         | Control user permissions       |
| Permission Sets  | Provide additional access      |
| Object Manager   | Configure Salesforce objects   |
| Schema Builder   | Design data relationships      |

---

# 8. Data Model

The main data entities are:

```text
             ┌─────────────┐
             │    Sender   │
             └──────┬──────┘
                    │
                    ▼
             ┌─────────────┐
             │    Parcel   │
             └──────┬──────┘
                    │
            ┌───────┴────────┐
            ▼                ▼
     ┌─────────────┐  ┌─────────────┐
     │  Receiver   │  │  Delivery   │
     └─────────────┘  └──────┬──────┘
                              │
                              ▼
                       Delivery Agent
```

---

# 9. Main Objects

## Parcel

The Parcel object stores the main shipment information.

Example fields:

* Parcel ID
* Parcel Name
* Status
* Sender
* Receiver
* Delivery Agent
* Booking Date
* Delivery Date

---

## Sender

Stores information about the person sending the parcel.

Example fields:

* Sender Name
* Phone
* Email
* Address

---

## Receiver

Stores information about the person receiving the parcel.

Example fields:

* Receiver Name
* Phone
* Email
* Address

---

## Delivery

Stores delivery-related information.

Example fields:

* Delivery ID
* Parcel
* Delivery Agent
* Delivery Status
* Delivery Date
* Delivery Remarks

---

# 10. Security Model

Security is implemented using Salesforce access-control features.

## Admin

Provides the highest level of system access.

```text
Admin
 ├── Manage Users
 ├── Manage Data
 ├── Configure Salesforce
 ├── Reports
 └── Security Management
```

## Delivery Agent

Can access parcels assigned to them and update delivery information.

```text
Delivery Agent
 ├── View Assigned Parcels
 ├── Update Status
 └── Confirm Delivery
```

## Customer Support

Can access customer and delivery information required for support operations.

```text
Customer Support
 ├── View Customer Information
 ├── View Parcel Information
 └── Handle Delivery Issues
```

## Customer

Customers should only access information appropriate to their own parcel activity.

```text
Customer
 ├── Create/Book Parcel
 ├── Track Parcel
 └── Receive Updates
```

---

# 11. Salesforce Automation

Salesforce Flow is used to automate repetitive processes.

### Example Status Automation

```text
Parcel Status Updated
        ↓
Salesforce Flow Triggered
        ↓
Check New Status
        ↓
Update Related Information
        ↓
Send Email / Notification
        ↓
Record Activity
```

This reduces manual intervention and improves consistency.

---

# 12. AI Integration

Swift Ship Tracker uses **Prompt Builder / Agentforce** to support intelligent parcel tracking.

### Example User Query

```text
"Where is my parcel SST-1001?"
```

### AI Processing

```text
User Query
    ↓
Agentforce
    ↓
Identify Parcel ID
    ↓
Retrieve Parcel Details
    ↓
Read Current Status
    ↓
Generate Response
```

### Example Response

```text
Parcel SST-1001 is currently In Transit.
```

The AI assistant can help customers and support teams obtain parcel information more quickly.

---

# 13. Reports and Dashboards

Administrators can use Salesforce Reports and Dashboards to monitor operations.

### Possible Reports

* Total Parcels
* Delivered Parcels
* Parcels In Transit
* Out-for-Delivery Parcels
* Delayed Deliveries
* Delivery Agent Performance
* Daily Parcel Bookings

### Dashboard Metrics

```text
Total Parcels
      ↓
In Transit
      ↓
Out for Delivery
      ↓
Delivered
      ↓
Delayed
```

These reports help administrators understand operational performance.

---

# 14. Customer Experience

Experience Cloud can be used to provide a customer-facing portal.

Customers can:

* Access their parcel information.
* Track shipments.
* View delivery status.
* Receive updates.
* Interact with AI assistance.

The portal provides a simple interface without requiring customers to access the internal Salesforce environment.

---

# 15. End-to-End System Workflow

```text
Customer
   ↓
Book Parcel
   ↓
Parcel Record Created
   ↓
Delivery Agent Assigned
   ↓
Booked
   ↓
In Transit
   ↓
Out for Delivery
   ↓
Delivered
   ↓
Customer Notification
   ↓
Dashboard Updated
```

---

# 16. Project Architecture

```text
                ┌─────────────────────┐
                │      Customer       │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │ Experience Cloud /  │
                │     Agentforce      │
                └──────────┬──────────┘
                           │
                           ▼
              ┌────────────────────────┐
              │       Salesforce       │
              │                        │
              │ Parcel                 │
              │ Sender                 │
              │ Receiver               │
              │ Delivery               │
              └───────────┬────────────┘
                          │
              ┌───────────┼────────────┐
              ▼           ▼            ▼
           Flows       Prompt       Reports
                       Builder      & Dashboards
              │           │            │
              ▼           ▼            ▼
          Automation      AI       Monitoring
```

---

# 17. Key Benefits

### For Customers

* Easy parcel tracking
* Faster access to shipment information
* Automated notifications
* AI-assisted support

### For Delivery Agents

* Easy access to assigned parcels
* Simple status updates
* Better delivery management

### For Customer Support

* Centralized customer information
* Faster query resolution
* Easy parcel-status checking

### For Administrators

* Centralized CRM
* Automated processes
* Reports and dashboards
* Secure user access

---

# 18. Testing

The system should be tested for:

* Parcel creation
* Sender and receiver information
* Status updates
* Flow automation
* Email notifications
* AI responses
* Reports
* User permissions
* Data access
* Security

### Example Test Case

```text
Test Case: Parcel Status Update

Input:
Parcel Status = In Transit

Expected Result:
1. Parcel status changes to In Transit.
2. Automation is triggered.
3. Notification is generated.
4. Updated information is available to authorized users.
```

---

# 19. Project Milestones

### Phase 1 — Requirement Analysis & Planning

* Defining Project Scope & Objectives
* Gathering & Analysing User Needs
* Identifying Key Salesforce Features & Tools Required
* Designing Data Model & Security Model

### Phase 2 — Salesforce Development

* Create objects
* Create fields
* Configure relationships
* Build automation
* Configure security

### Phase 3 — UI/UX Development

* Customer interface
* Salesforce pages
* Experience Cloud
* User experience customization

### Phase 4 — Testing & Security

* Functional testing
* Automation testing
* AI testing
* Security testing
* Data validation

### Phase 5 — Deployment & Documentation

* Final testing
* Deployment
* Documentation
* Demo preparation
* Project presentation

---

# 20. Project Status

| Module                   | Status         |
| ------------------------ | -------------- |
| Project Scope            | ✅ Completed    |
| User Requirements        | ✅ Completed    |
| Salesforce Features      | ✅ Completed    |
| Data Model Design        | ✅ Completed    |
| Security Model Design    | ✅ Completed    |
| Salesforce Configuration | 🔄 In Progress |
| Automation               | 🔄 In Progress |
| AI Integration           | 🔄 In Progress |
| Testing                  | 🔄 In Progress |
| Documentation            | 🔄 In Progress |

---

# 21. Future Enhancements

Future versions of Swift Ship Tracker can include:

* Real-time GPS-based tracking
* Mobile application
* Advanced delivery-time prediction
* AI-based delay prediction
* Route optimization
* Customer feedback and ratings
* Advanced analytics
* Integration with external courier APIs
* Multilingual AI assistance

---

# 22. Conclusion

Swift Ship Tracker provides a centralized Salesforce-based solution for managing parcel delivery operations. By combining **CRM, automation, AI, reporting, Experience Cloud, and security controls**, the system can improve parcel tracking, reduce manual work, and provide better visibility to customers, delivery agents, support teams, and administrators.

The project demonstrates how Salesforce can be used to build a scalable and intelligent parcel delivery management platform.

---

## Technologies Used

* Salesforce CRM
* Salesforce Developer Org
* Custom Objects
* Salesforce Flow Builder
* Prompt Builder
* Agentforce
* Experience Cloud
* Reports & Dashboards
* Profiles
* Permission Sets
* Google Docs
* Google Sheets

---

## Project Team

**Project:** Swift Ship Tracker
**Domain:** Salesforce CRM / Parcel Delivery Management
**Platform:** Salesforce
**AI Technology:** Prompt Builder / Agentforce
**Automation:** Salesforce Flow
**Status:** In Development
