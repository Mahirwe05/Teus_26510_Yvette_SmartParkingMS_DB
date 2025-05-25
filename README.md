## Name: MAHIRWE YVETTE
## ID:26510


# PL/SQL CAPSTONE PROJECT



## PHASE 1
# 🚗 SMART PARKING MANAGEMENT SYSTEM

## 📄 Project Description
This is a parking management system that is designed to **optimize parking space availability**,  
and **streamline the reservation process** in busy urban areas.

---

## ❗ Problem Definition and Problem Statement

"Current urban parking systems are inefficient, leading to traffic congestion, wasted fuel, and driver frustration. The problem is the lack of a real-time, automated system that helps drivers find and reserve parking spots efficiently. This project aims to develop a smart, database-driven solution that automates parking space management and improves user experience."

In many urban areas, drivers waste time and fuel searching for parking due to inefficient parking management. This leads to traffic congestion, environmental pollution, and driver frustration. The current manual or semi-automated systems lack real-time updates and reservation features. The goal of this project is to develop a smart, automated parking reservation system that provides real-time availability, booking features, and secure payment options to improve urban mobility and user convenience.



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
## PHASE  2
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

## 🌟 Why This Process Is Important for organizational efficiency.

- 🅿️ **Efficient use of parking spaces**  
- 🚦 **Reduces traffic and waiting times**  
- 💰 **Increases earnings by avoiding unused spaces**  
- 😀 **Enhances the customer experience**

> 💡 **Overall**, it makes managing public parking **smarter, faster, and more effective.**

---
## PHASE 3

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

## PHASE 4
Showing PDB and the user who has all privileges
![Screenshot 2025-05-08 155854](https://github.com/user-attachments/assets/c6b6423d-388a-4787-8394-f6a071773eb4)


## Oracle Enterprise Manager
![Screenshot 2025-05-08 170813](https://github.com/user-attachments/assets/4ea37c0c-d49b-4184-bc16-f54efef279aa)
![Screenshot 2025-05-08 170929](https://github.com/user-attachments/assets/8268fd80-dc61-4090-923d-289f985e2dc2)


## PHASE 5

## CREATING TABLES AND INSERTING DATA  IN THE TABLES

```SQL
CREATE TABLE Customer ( 
    CustomerID INT PRIMARY KEY, 
    Name VARCHAR2(100) NOT NULL, 
    Email VARCHAR2(100) UNIQUE NOT NULL, 
    PhoneNumber VARCHAR2(20) NOT NULL, 
    LicensePlate VARCHAR2(20) NOT NULL, 
    CONSTRAINT chk_customer_email CHECK (Email LIKE '%@%') 
);

-- PARKING LOT OPERATOR TABLE
CREATE TABLE ParkingLotOperator ( 
    OperatorID INT PRIMARY KEY, 
    Name VARCHAR2(100) NOT NULL, 
    ContactInformation VARCHAR2(150) NOT NULL 
);

-- PARKING SPACE TABLE
CREATE TABLE ParkingSpace ( 
    ParkingSpaceID INT PRIMARY KEY, 
    Location VARCHAR2(100) NOT NULL, 
    SlotNumber VARCHAR2(10) NOT NULL, 
    AvailabilityStatus VARCHAR2(20) NOT NULL, 
    ParkingType VARCHAR2(20) NOT NULL, 
    PricePerHour DECIMAL(6,2) NOT NULL, 
    OperatorID INT NOT NULL, 
    CONSTRAINT fk_parking_operator FOREIGN KEY (OperatorID) REFERENCES ParkingLotOperator(OperatorID),
    CONSTRAINT chk_availability CHECK (AvailabilityStatus IN ('Available', 'Occupied', 'Reserved')), 
    CONSTRAINT chk_parking_type CHECK (ParkingType IN ('Regular', 'Handicap', 'VIP', 'Electric Vehicle'))
);

-- RESERVATION TABLE
CREATE TABLE Reservation ( 
    ReservationID INT PRIMARY KEY, 
    CustomerID INT NOT NULL, 
    ParkingSpaceID INT NOT NULL, 
    StartTime DATE NOT NULL, 
    EndTime DATE NOT NULL, 
    PaymentStatus VARCHAR2(20) NOT NULL, 
    ReservationStatus VARCHAR2(20) NOT NULL, 
    CONSTRAINT fk_res_customer FOREIGN KEY (CustomerID) REFERENCES Customer(CustomerID), 
    CONSTRAINT fk_res_parking FOREIGN KEY (ParkingSpaceID) REFERENCES ParkingSpace(ParkingSpaceID), 
    CONSTRAINT chk_payment_sTables
tatus CHECK (PaymentStatus IN ('Paid', 'Pending', 'Failed')), 
    CONSTRAINT chk_reservation_status CHECK (ReservationStatus IN ('Confirmed', 'Canceled', 'Completed'))
);
CREATE TABLE Relationships (
    RelationshipID INT PRIMARY KEY,
    TableName VARCHAR2(100) NOT NULL,
    RelatedTableName VARCHAR2(100) NOT NULL,
    ForeignKeyColumn VARCHAR2(100) NOT NULL,
    ReferenceColumn VARCHAR2(100) NOT NULL,
    RelationshipDescription VARCHAR2(255) NOT NULL
);

DROP TABLE Relationships;
CREATE TABLE TableRelationships (
    RelationshipID INT PRIMARY KEY,
    SourceTable VARCHAR2(100) NOT NULL,
    TargetTable VARCHAR2(100) NOT NULL,
    SourceColumn VARCHAR2(100) NOT NULL,
    TargetColumn VARCHAR2(100) NOT NULL,
    RelationshipType VARCHAR2(50) NOT NULL,
    Description VARCHAR2(255)
);
-- INSERT INTO Customer
INSERT INTO Customer (CustomerID, Name, Email, PhoneNumber, LicensePlate)
VALUES (1, 'John Doe', 'john.doe@gmail.com', '1234567890', 'ABC123');

INSERT INTO Customer (CustomerID, Name, Email, PhoneNumber, LicensePlate)
VALUES (2, 'Jane Smith', 'jane.smith@gmail.com', '0987654321', 'XYZ789');

-- INSERT INTO ParkingLotOperator
INSERT INTO ParkingLotOperator (OperatorID, Name, ContactInformation)
VALUES (1, 'Mike Operator', 'mike.operator@gmail.com');

INSERT INTO ParkingLotOperator (OperatorID, Name, ContactInformation)
VALUES (2, 'Anna Admin', 'anna.admin@gmail.com');

-- INSERT INTO ParkingSpace
INSERT INTO ParkingSpace (ParkingSpaceID, Location, SlotNumber, AvailabilityStatus, ParkingType, PricePerHour, OperatorID)
VALUES (1, 'Lot A', 'A1', 'Available', 'Regular', 2.50, 1);

INSERT INTO ParkingSpace (ParkingSpaceID, Location, SlotNumber, AvailabilityStatus, ParkingType, PricePerHour, OperatorID)
VALUES (2, 'Lot B', 'B1', 'Occupied', 'VIP', 5.00, 2);

INSERT INTO ParkingSpace (ParkingSpaceID, Location, SlotNumber, AvailabilityStatus, ParkingType, PricePerHour, OperatorID)
VALUES (3, 'Lot A', 'A2', 'Reserved', 'Electric Vehicle', 3.00, 1);

-- INSERT INTO Reservation
INSERT INTO Reservation (ReservationID, CustomerID, ParkingSpaceID, StartTime, EndTime, PaymentStatus, ReservationStatus)
VALUES (1, 1, 1, TO_DATE('2025-05-08 08:00:00', 'YYYY-MM-DD HH24:MI:SS'), TO_DATE('2025-05-08 10:00:00', 'YYYY-MM-DD HH24:MI:SS'), 'Paid', 'Confirmed');

INSERT INTO Reservation (ReservationID, CustomerID, ParkingSpaceID, StartTime, EndTime, PaymentStatus, ReservationStatus)
VALUES (2, 2, 2, TO_DATE('2025-05-07 12:00:00', 'YYYY-MM-DD HH24:MI:SS'), TO_DATE('2025-05-07 14:00:00', 'YYYY-MM-DD HH24:MI:SS'), 'Pending', 'Canceled');
 
);
```

## SCREENSHOT OF THE TABLES CREATED, AND THE INSERTED ROWS.

![Screenshot 2025-05-08 190849](https://github.com/user-attachments/assets/76593952-8d44-4452-89ef-6aacad9a61eb)


## PHASE 6
## 📦  Database Interaction and Transactions
This phase focuses on executing robust database interactions in the Parking Reservation System, covering DDL/DML operations, analytics using window functions, and modular SQL programming using procedures, functions, cursors, and packages.

📌 Tasks & Deliverables
🔧 1. DDL & DML Operations
✅ DDL – Table Alteration & Deletion

## Add a new column to Reservation
```sql

ALTER TABLE Reservation ADD CreatedAt DATE DEFAULT SYSDATE;
```

## Drop a column from Reservation
```sql
ALTER TABLE Reservation DROP COLUMN CreatedAt;
```
## Drop the Reservation table
```sql
DROP TABLE Reservation;
```
✅ DML – Insert, Update, Delete

## Update the availability status of a parking space
```sql
UPDATE ParkingSpace 
SET AvailabilityStatus = 'Occupied' 
WHERE ParkingSpaceID = 1;
```
## Delete dependent reservation(s) before deleting customer
```sql
DELETE FROM Reservation 
WHERE CustomerID = 2;
```
## Then delete the customer
```sql
DELETE FROM Customer 
WHERE CustomerID = 2;
```
📊 2. Analytics Using Window Functions
## 🔍 Problem Statement:
## Analyze total number of reservations and hours reserved per customer, ranked by total hours.

```sql 
SELECT 
    c.Name,
    COUNT(r.ReservationID) OVER (PARTITION BY c.CustomerID) AS TotalReservations,
    SUM((r.EndTime - r.StartTime) * 24) OVER (PARTITION BY c.CustomerID) AS TotalHours
FROM 
    Customer c
JOIN 
    Reservation r ON c.CustomerID = r.CustomerID
ORDER BY 
    TotalHours DESC;

## 🛠️ 3. Stored Procedures, Functions & Exception Handling
```
## 🧩 Procedure – Fetch Reservations by Customer
```sql 
CREATE OR REPLACE PROCEDURE GetReservationsByCustomer(p_CustomerID IN NUMBER) IS
    CURSOR res_cursor IS
        SELECT * FROM Reservation WHERE CustomerID = p_CustomerID;
    res_row Reservation%ROWTYPE;
BEGIN
    OPEN res_cursor;
    LOOP
        FETCH res_cursor INTO res_row;
        EXIT WHEN res_cursor%NOTFOUND;
        DBMS_OUTPUT.PUT_LINE('ReservationID: ' || res_row.ReservationID || 
                             ', Status: ' || res_row.ReservationStatus || 
                             ', Time: ' || res_row.StartTime || ' to ' || res_row.EndTime);
    END LOOP;
    CLOSE res_cursor;
EXCEPTION
    WHEN OTHERS THEN
        DBMS_OUTPUT.PUT_LINE('Error: ' || SQLERRM);
END;
```

## 🧮 Function – Calculate Duration in Hours
```sql

CREATE OR REPLACE FUNCTION GetDurationHours(p_Start DATE, p_End DATE)
RETURN NUMBER IS
BEGIN
    RETURN (p_End - p_Start) * 24;
END;
```
## 📦 4. Package for Modularization
## 🔐 Package Specification
```sql

CREATE OR REPLACE PACKAGE ReservationPkg IS
    PROCEDURE GetReservationsByCustomer(p_CustomerID IN NUMBER);
    FUNCTION GetDurationHours(p_Start DATE, p_End DATE) RETURN NUMBER;
END ReservationPkg;
```
## 🔧 Package Body
```sql
CREATE OR REPLACE PACKAGE BODY ReservationPkg IS

    PROCEDURE GetReservationsByCustomer(p_CustomerID IN NUMBER) IS
        CURSOR res_cursor IS
            SELECT * FROM Reservation WHERE CustomerID = p_CustomerID;
        res_row Reservation%ROWTYPE;
    BEGIN
        OPEN res_cursor;
        LOOP
            FETCH res_cursor INTO res_row;
            EXIT WHEN res_cursor%NOTFOUND;
            DBMS_OUTPUT.PUT_LINE('ReservationID: ' || res_row.ReservationID || 
                                 ', Status: ' || res_row.ReservationStatus || 
                                 ', Time: ' || res_row.StartTime || ' to ' || res_row.EndTime);
        END LOOP;
        CLOSE res_cursor;
    EXCEPTION
        WHEN OTHERS THEN
            DBMS_OUTPUT.PUT_LINE('Error: ' || SQLERRM);
    END;


    FUNCTION GetDurationHours(p_Start DATE, p_End DATE)
    RETURN NUMBER IS
    BEGIN
        RETURN (p_End - p_Start) * 24;
    END;

END ReservationPkg;
```
## 🧪 5. Testing

## Execute procedure
```sql
 EXEC ReservationPkg.GetReservationsByCustomer(1);
```
##  Test function output
```sql
SELECT ReservationPkg.GetDurationHours(
    TO_DATE('2025-05-08 08:00:00', 'YYYY-MM-DD HH24:MI:SS'),
    TO_DATE('2025-05-08 10:00:00', 'YYYY-MM-DD HH24:MI:SS')
) AS DurationHours FROM dual;
```
## PHASE 7

## 🔐 Advanced Database Programming and Auditing



### 🧩 1. Problem Statement

#### 🚧 Real-world Challenge:
The system must prevent unauthorized or risky changes to important database tables, especially during business-sensitive
periods like weekdays and public holidays.

#### ✅ Objectives:
- Stop employees from making any **INSERT**, **UPDATE**, or **DELETE** actions during weekdays (Monday to Friday).
- Also block actions on predefined **public holidays** within the upcoming month.
- Track all modification attempts in a dedicated **audit log** with details like user ID, timestamp, action type, and status (allowed or denied).

#### 🔧 Why Use Triggers, Packages, and Auditing?
- **Triggers** allow real-time enforcement of restrictions at the database level.
- **Packages** group logic (functions/procedures) for reuse and clean design.
- **Auditing** logs all user actions for traceability, which is essential in a system handling sensitive data like vehicle reservations and payments.

---

### 📅 2. Holiday Reference Table

```sql
CREATE TABLE HolidayList (
    HolidayDate DATE PRIMARY KEY,
    Description VARCHAR2(100)
);

-- Insert some upcoming holidays (update these accordingly)
INSERT INTO HolidayList VALUES (TO_DATE('2025-05-17', 'YYYY-MM-DD'), 'Independence Day');
INSERT INTO HolidayList VALUES (TO_DATE('2025-05-27', 'YYYY-MM-DD'), 'Memorial Day');
```
## 🚫 3. Restriction Trigger: Block Weekday + Holiday Manipulation
```sql

CREATE OR REPLACE TRIGGER trg_block_employee_changes
BEFORE INSERT OR UPDATE OR DELETE ON Reservation
BEGIN
    IF TO_CHAR(SYSDATE, 'DY') IN ('MON', 'TUE', 'WED', 'THU', 'FRI') OR
       EXISTS (
           SELECT 1 FROM HolidayList
           WHERE HolidayDate = TRUNC(SYSDATE)
       ) THEN
        RAISE_APPLICATION_ERROR(-20001, 'Operation not allowed during weekdays or public holidays.');
    END IF;
END;
```
## This trigger checks if today is a weekday or listed holiday, and blocks any modifications accordingly.

## 📦 4. Auditing Table & Audit Logic
```sql
CREATE TABLE AuditLog (
    LogID NUMBER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    UserID VARCHAR2(50),
    ActionType VARCHAR2(20),
    ActionTime TIMESTAMP,
    Operation VARCHAR2(20),
    Status VARCHAR2(10)
);
```
## 🔧 Function for Auditing
```sql

CREATE OR REPLACE FUNCTION log_audit(
    p_user_id VARCHAR2,
    p_action_type VARCHAR2,
    p_operation VARCHAR2,
    p_status VARCHAR2
) RETURN NUMBER IS
BEGIN
    INSERT INTO AuditLog (UserID, ActionType, ActionTime, Operation, Status)
    VALUES (p_user_id, p_action_type, SYSTIMESTAMP, p_operation, p_status);
    RETURN 1;
END;
```

## 🔐 Trigger with Logging
```sql
CREATE OR REPLACE TRIGGER trg_secure_reservation_changes
BEFORE INSERT OR UPDATE OR DELETE ON Reservation
DECLARE
    v_status VARCHAR2(10);
    v_user VARCHAR2(50) := SYS_CONTEXT('USERENV', 'SESSION_USER');
BEGIN
    IF TO_CHAR(SYSDATE, 'DY') IN ('MON', 'TUE', 'WED', 'THU', 'FRI') OR
       EXISTS (
           SELECT 1 FROM HolidayList
           WHERE HolidayDate = TRUNC(SYSDATE)
       ) THEN
        v_status := 'Denied';
        log_audit(v_user, 'Blocked Attempt', ORA_SYSEVENT, v_status);
        RAISE_APPLICATION_ERROR(-20002, 'Modifications blocked during restricted periods.');
    ELSE
        v_status := 'Allowed';
        log_audit(v_user, 'Data Change', ORA_SYSEVENT, v_status);
    END IF;
END;
```
## 🔍 5. How This Improves the System
🔐 Security: Prevents data tampering during critical periods

📋 Accountability: Tracks who attempted what and when

🛠️ Automation: Automatically enforces rules with no manual monitoring

🧩 Scalability: Logic can be reused through packages and functions

## 🧪 6. Testing the Logic
Try this query during a weekday or holiday:

```sql
DELETE FROM Reservation WHERE ReservationID = 1;
```
## Expected Result:

ORA-20002: Modifications blocked during restricted periods.

## Check the log:


```sql
 SELECT * FROM AuditLog ORDER BY ActionTime DESC;
```

## ✅ Inshort
Feature	Description
🛑 Trigger	Prevents changes on weekdays/holidays
📋 Audit Table	Records all attempts
📦 Function	Used to insert audit records
📊 Logging	Captures user, time, operation, and status

## Normalization

| **1NF (First Normal Form)**  | Eliminate repeating groups. Each column should hold atomic (indivisible) values.                                                     |
| **2NF (Second Normal Form)** | Be in 1NF and remove **partial dependencies** (i.e., non-key attributes must depend on the whole primary key).
| **3NF (Third Normal Form)**  | Be in 2NF and remove **transitive dependencies** (i.e., non-key → non-key).                                    



