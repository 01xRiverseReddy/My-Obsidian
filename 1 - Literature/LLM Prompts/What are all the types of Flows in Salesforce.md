Salesforce provides several types of **flows** as part of its **Flow Builder** automation tool. Each flow type serves different purposes based on **when** and **how** it runs.

Here’s a breakdown of the **different types of flows** in Salesforce:

---

### **1. Screen Flow**
- **Purpose**: Used when **user interaction** is required.
- **Runs in UI**: Yes
- **Examples**:
  - Step-by-step data entry forms
  - Lead qualification wizards
  - Guided scripts for call center agents

**Launch From**:
- Lightning Page
- Quick Action
- Flow Component
- Experience Cloud Site

---

### **2. Auto-Launched Flow (No Trigger)**
- **Purpose**: Background automation that doesn’t need user interaction or a specific trigger.
- **Runs in UI**: No
- **Examples**:
  - Called from Apex
  - Used as Subflows
  - Scheduled jobs or REST API calls

**Launch From**:
- Apex
- Process Builder
- Subflow
- Custom button or REST call

---

### **3. Record-Triggered Flow**
- **Purpose**: Executes automatically **when a record is created, updated, or deleted**.
- **Runs in UI**: No (background)
- **Examples**:
  - Update a contact when the related account changes
  - Auto-assign tasks when a lead status is changed

**Trigger Events**:
- On Create
- On Update
- On Delete (as of Spring '21)

**Modes**:
- **Before Save**: Faster; used to update the same record
- **After Save**: Used for related record operations

---

### **4. Scheduled-Triggered Flow**
- **Purpose**: Runs **at a scheduled time** or at regular intervals.
- **Runs in UI**: No
- **Examples**:
  - Daily summary emails
  - Monthly data clean-up
  - Auto-closing stale cases

**Trigger**: Time-based (e.g., every day at 1 AM)

**Supports Filtering**: Yes (to define which records to act on)

---

### **5. Platform Event-Triggered Flow**
- **Purpose**: Responds to a **Platform Event** being published.
- **Runs in UI**: No
- **Examples**:
  - Update UI after external system sends data
  - Create a task when a system integration publishes an event

**Trigger**: Event messages (via API or Apex)

---

### **6. Autolaunched Flow with Triggered Orchestration**
- **Purpose**: Used as **steps in Flow Orchestrator**, which allows you to coordinate **multi-user, multi-step** processes.
- **Runs in UI**: Depends on the orchestration
- **Examples**:
  - Multi-approver onboarding process
  - Escalation flow with approvals and manual steps

---

### **7. Subflow (Reusable Flow)**
- **Purpose**: A flow that is designed to be **called from other flows**.
- **Type**: Can be Auto-launched or Screen Flow
- **Examples**:
  - Reusable address validation logic
  - Common task creation logic across multiple flows

---

### **Summary Table**

| Flow Type | Trigger | User Interaction | Common Use |
|-----------|---------|------------------|-------------|
| **Screen Flow** | Manual | Yes | Guided UIs, wizards |
| **Auto-Launched Flow** | Manual | No | Apex calls, subflows |
| **Record-Triggered Flow** | Record create/update/delete | No | Data automation |
| **Scheduled Flow** | Time-based | No | Periodic tasks |
| **Platform Event Flow** | Event trigger | No | Reactive to external systems |
| **Orchestration Flow** | Orchestration step | Depends | Multi-user processes |
| **Subflow** | Called by another flow | Depends | Reusable logic |

---

Let me know if you want **architecture diagrams**, **comparison with Apex/Process Builder**, or real-world **design patterns** using these flows!