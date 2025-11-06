🏥 Medical Inventory Management System (Salesforce)

📘 Introduction
The Medical Inventory Management System is a Salesforce-based application designed to manage and automate medical supply chain operations for hospitals, clinics, and healthcare organizations.  
It enables efficient tracking of medicines, equipment, and consumables, ensuring the right supplies are always available when needed.

Built using the Salesforce Developer Edition, this system showcases the power of Salesforce CRM for healthcare automation — combining custom objects, Flows, Apex, validation rules, and dashboards for a complete real-time management solution.


🎯 Objectives
- Maintain accurate, real-time inventory records of medical items  
- Automate procurement and generate purchase orders instantly  
- Optimize supply distribution across departments and locations  
- Eliminate manual errors using validation rules and workflows  
- Secure access using role-based permissions  
- Support decision-making with analytical dashboards  
- Guarantee availability of essential medicines for patient safety  


💡 Ideation

Originality of the Idea
Unlike traditional CRM use cases, this project targets **healthcare-specific inventory challenges** such as stock shortages, expiry wastage, and overstocking.  
The solution integrates Salesforce features innovatively:
- Custom Objects and Relationships  
- Flows for automation  
- Apex Triggers and Handlers  
- Validation Rules  
- Role-based Access Control  
- Reports and Dashboards  

Feasibility
- Fully achievable in **Salesforce Developer Edition** (free)
- No external tools or paid licenses required  
- Scalable for hospitals, clinics, and NGOs  
- Supports future integration with **IoT, AI/ML, ERP systems**


⚙️ System Design

Custom Objects
1. Product – Tracks medicine/equipment details  
2. PurchaseOrder – Records procurement information  
3. OrderItem – Links purchase orders with individual products  
4. InventoryTransaction – Tracks movement of stock  
5. Supplier – Maintains supplier details  

Tabs
Product, PurchaseOrder, OrderItem, InventoryTransaction, Supplier

User Roles
- Admin – Full system access  
- Inventory Manager – Manages product stock and transactions  
- Purchase Manager – Handles purchase orders and suppliers  
- Pharmacist/Nurse – Views limited data relevant to department  


🧩 Features & Automation

Apex Trigger & Handler
Automatically calculates total order cost from order items:
apex
trigger CalculateTotalAmountTrigger on Order_Item__c (after insert, after update, after delete, after undelete) {
    CalculateTotalAmountHandler.calculateTotal(
        Trigger.new, Trigger.old,
        Trigger.isInsert, Trigger.isUpdate,
        Trigger.isDelete, Trigger.isUndelete
    );
}
Flow Automation
Flow Name: ActualDeliveryDateUpdating
Trigger: On creation/update of Purchase Order
Action: Auto-calculates Actual Delivery Date = Order Date + 3 days

Validation Rule Example

Rule Name: ExpectedDeliveryDateValidation
Object: Purchase Order
Formula: (Expected_Delivery_Date__c - Order_Date__c) > 7
Error Message: "The Expected Delivery Date should not exceed 7 days."

📊 Reports & Dashboards
Reports
- Purchase Orders by Suppliers (Summary)
- Grouped by Supplier ID and Purchase Order ID
- Displays total orders and costs
- Complete Purchase Details Report
- Includes Product ID, Name, Quantity Received, and Amount

Dashboard
- MedicalInventoryDashboard
- Displays charts and summaries from reports
- Offers insights on procurement efficiency, supplier performance, and stock health

🧠 Best Use Cases

- Hospitals: ICU drugs, surgical tools, and daily consumables
- Clinics & Pharmacies: Medicine stock and expiry alerts
- Blood Banks: Donor and expiry tracking for blood units
- NGOs & Relief Camps: Donation distribution management
- Government Health Departments: Centralized drug tracking
- Medical Colleges: Training on healthcare IT & CRM systems

✅ Conclusion
The Medical Inventory Management System successfully addresses major healthcare supply challenges through Salesforce’s low-code ecosystem.
It ensures:

- Accurate and secure inventory management
- Reduced manual errors
- Automated procurement
- Actionable data insights

🔮 Future Scope

- IoT for live warehouse monitoring
- AI/ML for predictive restocking
- Mobile app integration for field access
- ERP/HMS connectivity for enterprise expansion

📚 References

- Salesforce Custom Objects
- Validation Rules
- Apex Triggers
- Flow Basics
- Reports and Dashboards

👩‍💻 Developed Using

- Platform: Salesforce Developer Edition
- Languages: Apex, SOQL, Lightning App Builder
- Automation: Flows, Validation Rules, Process Builder
- Reports & Dashboards: Salesforce Analytics

🏷️ Author
Developed by 
   Kamala V
   Masaniselvi G
   Tejashree S
   Prabha T
 
 📅 Year: 2025
🔗 GitHub Repository: https://github.com/MasaniselviGanesan/Naan-Mudhalvan
