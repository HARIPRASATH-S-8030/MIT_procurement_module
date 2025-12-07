**Procurement Module (AI/ML SIP Industry-Oriented Project)**

📝 **Overview**

This repository contains the Procurement Module designed for the AI/ML – Signal and Image Processing (SIP) industry-oriented course.
The module follows best practices in software engineering, focusing on:

Clean architecture

Modular Python design

Version control via GitHub

Cloud-ready backend development

Integration with notifications, payments, and authentication



---

📂 **Directory Structure**

procurement_module/
│
├── procurement_main.py # Main controller, connects config + libs + utilities
├── lib.py # All classes (action logic)
├── config.py # Static configuration values (username, password, etc)
└── utility.py # Notification utilities (WhatsApp, SMS, Email)

**1. procurement_main.py**

Responsible for:

Initializing classes

Fetching username/password from config

Calling external API endpoints

Handling output and responses


Example flow:

from config import username, password
from lib import Login

# Example API: mit.com/api/fetch_homepage

login_obj = Login(username, password)
login_obj.check_username()


---

**2. lib.py — Action Classes**

Contains all business logic implemented as classes using OOPS.

Example:

class Login:
    def __init__(self, username, password):
        self.username = username
        self.password = password

    def check_username(self):
        if len(self.username) < 7:
            raise ValueError("Username too short")
        return True


---

**3. config.py — Static Configuration**

Stores static values required across modules.

Example:

username = "hari_prasad"
password = "mit123"


---

**4. utility.py — Notification Services**

Implements functions for:

WhatsApp notifications

SMS alerts

Email alerts


These will be used for:

Login authentication

Vendor alerts

Supervisor notifications

Approval workflows



---

**🧑‍💻 Best Coding Practices Used**

Object Oriented Programming (OOPS)

No hardcoding (all values stored in config.py)

Logging for debugging and tracking

Exception handling (try/except/else/finally)

Clean API interaction layer

Modular folder structure

GitHub version control for teamwork



---

**🛠️ Tech Stack**

Component Technology

Backend Python
API Framework Flask
Database MongoDB (using PyMongo)
Frontend HTML, CSS
Notifications WhatsApp / SMS / Email
Authentication Multi-Factor Authentication (MFA)



---

**🌐 API Example**

Endpoint:

mit.com/api/fetch_homepage

Process flow:

1. API calls a class method from lib.py


2. Creates a login object


3. Validates username


4. Returns success/failure




---

**☁️ Initial Setup Requirements**
Cloud deployment environment

MongoDB setup

Domain configuration

WhatsApp notification setup

SMS gateway integration

Email system configuration

Payment Gateway setup

Multi-Factor Authentication (OTP-based)



---

**🧾 Procurement Module Workflow**

1. Request Creation

Person A logs into the tool

Asks for quotes from multiple vendors

Notifications sent via email + WhatsApp


2. Vendor Response

Vendors submit quotes in the tool

Notifications sent again


3. Supervisor Approval

Person A submits request + quote

Supervisor can:

Approve

Reject

Forward to next level


Digital signature included


4. Post-Approval Flow

Purchase order generated

Payment processed

GST information updated

Vendor informed

Order tracking happens

Product received

Invoice uploaded

Item added to inventory (after Inventory Module is ready)



---

**📊 Dashboard Features**

Search

Order status tracking

Summary report



---

**🗄️ Database Design (MongoDB)**

Stores:

User details + supervisor + access permissions

Equipment list, configurations, prices

Vendor details

Supervisor and approval hierarchy

Transaction details

Approval rules

SLA monitoring


Approval example:

If amount > 20,000 → escalate to Director


---

**🔧 Sub-Modules**

Login with MFA

Budget Management

Vendor Onboarding and Contract Management

Database Management (Backup, Archiving, Restoration)

Quote Module

Order Placement

Payment Module

Dashboard



---

**⚠️ Notes**

SLA for supervisor response

SLA for vendor response

Role-based access control

Every transaction must be logged and authenticated

Expected to have 20+ web pages

Added README.md for procurement module.
