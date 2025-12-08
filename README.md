# **Procurement Module**
A comprehensive procurement management system designed to streamline equipment requisition, vendor quote collection, approval workflows, and purchase order management. The platform enables organizations to manage the complete procurement lifecycle with role-based access control, multi-factor authentication, and real-time notifications.

## **Overview**
The procurement module facilitates a complete end-to-end procurement workflow that connects requesters, supervisors, vendors, and finance teams. The system maintains transparency through automated notifications, digital signatures, and comprehensive tracking of all transactions.

## **Key Features**
### **User Management & Authentication**

Multi-factor authentication (OTP-based)

Role-based access control

Supervisor and requestor hierarchies

Digital signature support for approvals

### **Procurement Workflow**

Equipment request submission with justification

Multi-vendor quote collection

Approval routing with SLA tracking

Purchase order creation and management

Real-time order status tracking

Invoice management and documentation

### **Vendor Management**

Vendor onboarding and profile management

Vendor contract management

Performance tracking and rating

Automated vendor notifications

### **Financial Management**

Budget tracking and allocation

GST tracking and compliance

Payment gateway integration

Approval thresholds (e.g., amounts exceeding ₹20k require director approval)

Transaction history and audit trail

### **Dashboard & Reporting**

Equipment search functionality

Order status tracking

Summary reports and analytics

Inventory integration (post-implementation)

## **Technology Stack**
| Component     | Technology           |
| ------------- | -------------------- |
| Backend	    | Python               |
|API Framework  |	Flask              |
|Database	    | MongoDB (PyMongo)    |
|Frontend	    | HTML, CSS            |
|Authentication |	OTP-based MFA      |
|Notifications	| Email, SMS, WhatsApp |

## **Architecture**

### **Directory Structure**
```
procurement/
├── procurement_main.py      # Entry point - orchestrates API calls
├── lib.py                   # Core classes and business logic
├── config.py                # Static configuration (credentials, settings)
├── utility.py               # Notification handlers (Email, SMS, WhatsApp)
└── templates/               # HTML/CSS frontend files
```
### **Code Organization**

**1. procurement_main.py**

Sources configuration from config.py

Initializes library objects

Orchestrates API calls

Handles API responses


**2. lib.py**

Contains all business logic classes

Implements procurement operations

Example: Login validation, quote processing, approval workflows


**3. config.py**

Centralized static configuration

Username/password management

Database connection strings

API endpoints

Notification credentials


**4. utility.py**

Email notification service

SMS notification service

WhatsApp notification service

## **API Endpoints**
The Flask backend exposes RESTful API endpoints following the pattern:
```
MIT.com/api/endpoint_name
```

Example workflow:

python
API call
GET /api/fetch_homepage

Backend processing
my_login = Login(username, password)
result = my_login.check_username()

Response
return {'status': True/False}

## **Procurement Workflow Steps**

1.Request Creation - User submits equipment request with business justification

2. Quote Collection - Vendor quotes are collected through the platform; stakeholders notified via email and WhatsApp

3. Approval Request - Requestor submits quotes to supervisor with justification

4. Approval Decision - Supervisor reviews and approves/rejects/escalates using digital signature

5. Purchase Order - Approved requests converted to purchase orders

6. Payment Processing - Payment handled through integrated gateway with GST tracking

7. Vendor Notification - Vendor informed of order placement

8. Order Tracking - Real-time tracking of delivery status

9. Product Receipt - Received equipment documented with photos and details

10. Inventory Integration - Equipment added to inventory system with metadata

11. Dashboard Management - Complete visibility through search, status checks, and reporting

## **Core Modules**
- Authentication Module - Multi-factor OTP-based login

- Budget Management - Track and enforce budget allocations

- Vendor Management - Onboarding, contracts, and performance tracking

- Database Management - Backup, archiving, and restoration

- Quote Module - Collect and compare vendor quotes

- Order Placement - Create and manage purchase orders

- Payment Module - Process payments with GST compliance

- Dashboard - Analytics and reporting interface

## **Database Schema**
The system maintains the following data entities:

- Users - Requestors, supervisors, and their access permissions

- Equipment - Equipment catalog with types, configurations, and pricing

- Vendors - Vendor details, contracts, and approval status

- Supervisors - Supervisor details and approval authority

- Transactions - Complete transaction history and audit trail

- Approval Settings - Rules for approval routing (e.g., amount thresholds)

## **Best Practices**
- Object-Oriented Design - All code follows OOPS principles

- Comprehensive Logging - Detailed logging for debugging and audit trails

- No Hardcoding - All configuration externalized to config.py

- Exception Handling - Try-except-else-finally blocks for robust error handling

- Version Control - Git-based version control for all code changes

- Quality First - Quality-focused development without rigid time constraints

## **Setup & Configuration**

**Initial Setup Steps**

1. Cloud Infrastructure - Deploy on cloud platform

2. Database Setup - Configure MongoDB instance and initialize schema

3. Domain Configuration - Set up domain and SSL certificates

4. Notification Services - Configure WhatsApp, SMS, and email providers

5. Payment Gateway - Integrate payment processing gateway

6. Authentication - Setup OTP service and MFA system

## **Configuration File Example**
```
config.py
USERNAME = "your_username"
PASSWORD = "your_password"
MONGODB_URI = "mongodb://connection_string"
FLASK_API_BASE = "https://yourdomain.com/api"
PAYMENT_GATEWAY_KEY = "your_key"
```

## **Business Rules & Constraints**
- SLA Compliance - Service level agreements for supervisor approvals and vendor responses

- Role-Based Access - Users can only access operations matching their role

- Approval Thresholds - Purchase amounts exceeding defined limits require escalation

- Authentication Requirements - All transactions require authentication and authorization

- Notification Requirement - All state changes trigger stakeholder notifications

## **Scope**
The system comprises over 20 web pages across the complete procurement lifecycle with extensive dashboard capabilities for search, order tracking, and reporting. The inventory module is planned for future integration.

## **Contributing**
Follow the established best practices: maintain OOPS principles, add comprehensive logging, avoid hardcoding, and implement robust exception handling. All changes must be committed to the Git repository with clear commit messages.

## **Notes**
The procurement module is designed with quality as the primary focus, not time constraints

All code follows industry best practices for security, logging, and maintainability

Integration with inventory management is planned for future releases
