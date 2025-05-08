## Phase 1
# 🚗 SMART PARKING MANAGEMENT SYSTEM

## 📄 Project Description
This is a parking management system that is designed to **optimize parking space availability**,  
and **streamline the reservation process** in busy urban areas.

---

## ❗ Problem Definition

- 🚦 **Traffic Congestion & Wasted Time**  
- 🅿️ **Inefficient Parking Space Utilization**  
- 🚫 **Unauthorized Parking & Security Issues**

---

## 🌍 Context: Where and How?

- 📍 **Where?** Public parking spaces  
- ⚙️ **How?** By optimizing parking space availability and boosting the reservation process.

---

## 🎯 Target Users

- 👨‍✈️ **Drivers**  
- 🏢 **Companies that control public parking spaces**

---

## 🎯 Objectives

- 📈 **Maximize Parking Efficiency**: Utilize available spaces effectively.  
- 📅 **Simplify Reservations**: Allow users to book parking spots in advance.  
- 😀 **Enhance User Experience**: Provide a smooth and convenient parking process.  
- 🚗🔄 **Reduce Traffic Congestion**: Minimize vehicle movement in search of parking.

---
## Phase 2
# 📌 1. Define the Scope

## 📊 Relevance to MIS
This process involves **real-time data collection, storage, and analysis** to manage reservations, optimize space utilization, and generate operational reports that support strategic decision-making for both users and parking lot operators.

---

## 🎯 Objectives of the Process

- 🔍 Enable customers to search, reserve, and pay for parking spots online.  
- 📡 Provide real-time updates on parking availability.  
- 👨‍💼 Allow parking operators to monitor and manage spaces, adjust pricing, and generate usage reports.  
- 📈 Enhance decision-making through dashboards and reports (e.g., high-demand areas, usage trends).

---

## ✅ Expected Outcomes

- 🅿️ Efficient utilization of parking spaces.  
- 🚗 Reduced traffic and time spent searching for parking.  
- 💰 Increased revenue for operators.  
- 😀 Improved customer satisfaction and user experience.

---

## 🏢 Key Departments

### 📅 RESERVATION DEPARTMENT
- Tracks the booking and reservation process  
- Validates availability  
- Records start/end times and updates reservation status  

### 💳 PAYMENT DEPARTMENT
- Handles secure online transactions  
- Updates payment status in the system  

---

# 🧾 2. Identify Key Entities

| 🧍 Entity               | 🛠️ Responsibility                                                                 |
|------------------------|------------------------------------------------------------------------------------|
| 👤 **Customer (Driver)**     | - Creates account and logs in  <br> - Searches for available parking spots <br> - Makes reservations and payments |
| 📅 **Reservation System**   | - Manages the booking process <br> - Validates availability <br> - Records start/end times and updates reservation status |
| 💳 **Payment Processor**    | - Handles secure online transactions <br> - Updates payment status in the system |
| 🏢 **Parking Lot Operator** | - Monitors usage via dashboards <br> - Manages pricing and policies <br> - Receives reports on occupancy and revenue |

---
## BPMN DIAGRAM

![Screenshot 2025-05-08 183636](https://github.com/user-attachments/assets/0b638655-1003-4a43-9245-3d340a6bbefc)

## Smart Parking Management System – Process Description 

This diagram shows how the Smart Parking Management System works, with three main parts: 

 Customer (Driver) 

 Reservation System 

 Payment Processor 

The process starts when a customer creates an account. They can either cancel or log in. After logging in, the customer searches for available parking spaces in a certain area. This request goes to the Reservation System, which checks if a slot is available. 

 

## If a parking lot is available, the system: 


- ✅ **Validates the space**
- 🔄 **Updates the reservation status**
- ✉️ **Sends a confirmation message to the customer**
- 💬 **Asks the customer to make a payment**

### ❌ If the slot is **not available**:
- 📭 Sends an **unavailability message**
- 🚫 Declines the customer’s request

---

## 💳 Payment Flow

- When the customer proceeds to payment, they can choose:
  - 💳 **Card**
  - 📱 **Mobile Money (MoMo)**

- The **Payment Processor** handles the transaction.
  - ✅ If successful:
    - 💸 Account is debited
    - 📢 System confirms the parking is ready
    - 🚗 Customer can now park their car

---

## 🧠 How This Supports MIS (Management Information Systems)

- 🧭 **Makes decisions easier** – real-time updates help the system and users know what to do next  
- ⏱ **Saves time** – faster than manual processes  
- 🔗 **Connects data** – customer info, availability, and payments all in one place  
- 📊 **Supports future planning** – system collects data for reports and improvements  

---

## 🌟 Why This Process Is Important

- 🅿️ **Efficient use of parking spaces**  
- 🚦 **Reduces traffic and waiting times**  
- 💰 **Increases earnings by avoiding unused spaces**  
- 😀 **Enhances the customer experience**

> 💡 **Overall**, it makes managing public parking **smarter, faster, and more effective.**

---
## Phase 2

# 🔗 1. Entity-Relationship (ER) Model

---

## 📌 Entities and Attributes

| 🧱 Entity               | 🧬 Attributes                                                                                      |
|------------------------|----------------------------------------------------------------------------------------------------|
| 👤 **Customer**              | CustomerID (PK, INT), Name (VARCHAR2(100)), Email (VARCHAR2(100)), PhoneNumber (VARCHAR2(20)), LicensePlate (VARCHAR2(20)) |
| 🧑‍💼 **Parking Lot Operator** | OperatorID (PK, INT), Name (VARCHAR2(100)), ContactInformation (VARCHAR2(150))                |
| 🅿️ **Parking Space**         | ParkingSpaceID (PK, INT), Location (VARCHAR2(100)), SlotNumber (VARCHAR2(10)), AvailabilityStatus (VARCHAR2(20)), ParkingType (VARCHAR2(20)), PricePerHour (DECIMAL(6,2)), OperatorID (FK) |
| 📅 **Reservation**           | ReservationID (PK, INT), CustomerID (FK), ParkingSpaceID (FK), StartTime (DATE), EndTime (DATE), PaymentStatus (VARCHAR2(20)), ReservationStatus (VARCHAR2(20)) |

---

## 🔁 Relationships & Constraints

### 📊 Relationships

| 🔗 Relationship                        | 🔢 Type     | 📝 Details                                                  |
|---------------------------------------|------------|-------------------------------------------------------------|
| Customer → Reservation                | 1 : Many   | A customer can have multiple reservations.                 |
| ParkingSpace → Reservation            | 1 : Many   | A parking space can be reserved multiple times.            |
| ParkingLotOperator → ParkingSpace     | 1 : Many   | An operator manages multiple parking spaces.               |

---

### 🧷 Constraints Applied

| 🔐 Constraint Type | 📌 Description                                                                 |
|--------------------|---------------------------------------------------------------------------------|
| ❗ Not Null         | Name, Email, PhoneNumber (in Customer table)                                   |
| 🔑 Primary Key      | Each entity has a unique identifier (e.g., CustomerID, OperatorID)             |
| 🔁 Foreign Key      | Enforce links: Reservation → Customer, ParkingSpace → Operator, etc.          |
| 🔍 Unique           | Email must be unique in the Customer table                                     |
| ✅ Check            | Ensures allowed values for: AvailabilityStatus, ParkingType, PaymentStatus, ReservationStatus |

---

## 🧾 Data Types

| 📦 Data Type  | 🔍 Used For                                          |
|---------------|------------------------------------------------------|
| `INT`         | IDs and identifiers                                 |
| `VARCHAR2`    | Text fields (names, emails, phone numbers, etc.)    |
| `DECIMAL(6,2)`| Prices (


## ER DIAGRAM 
![Screenshot 2025-05-08 155304](https://github.com/user-attachments/assets/123e6827-556f-4207-848e-b518150760b9)

