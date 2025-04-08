# Practical-no.-6

**Modeling UML Class Diagrams**  
*Structural and Behavioral aspects | Class diagram | Elements in class diagram | Class | Relationships | Draw Class Diagram*

---

### **Aim of the Experiment:**  
To model the structural and behavioral aspects of the Ayurvedic Management System using UML class diagrams, showcasing the various classes, their attributes, methods, and relationships among them.

---

### **Introduction:**  
In software design, class diagrams are essential for visualizing the structure of a system. For the **Ayurvedic Management System**, the class diagram helps depict the core components such as patients, doctors, appointments, medicines, and treatment plans. It provides a blueprint of the system’s architecture by defining the classes, their properties, methods, and the interrelationships that enable smooth data and process flow.

---

### **Objectives:**  
After completing this experiment, you will be able to:  
- Graphically represent a class and its attributes and behaviors.  
- Establish associations among different classes relevant to the Ayurvedic domain.  
- Identify and represent the logical sequence of operations within the system.  
- Enhance understanding of system modularity through object-oriented design.

---

### **Theory**

#### **Structural and Behavioral Aspects:**  
- **Structural aspects** involve the organization of classes, their properties, and relationships.  
- **Behavioral aspects** involve how these classes interact and behave over time during the execution of operations.

#### **Class Diagram:**  
A class diagram for the Ayurvedic Management System typically includes the following classes:  
- **Patient**  
- **Doctor**  
- **Appointment**  
- **Medicine**  
- **Treatment Plan**  
- **Billing**  
- **Admin**

#### **Elements in Class Diagram:**  
- **Class Name**  
- **Attributes (variables like name, age, etc.)**  
- **Methods (functions like bookAppointment(), prescribeMedicine())**

#### **Relationships:**  
- **Association:** A patient can book multiple appointments.  
- **Aggregation:** A treatment plan includes multiple medicines.  
- **Composition:** A bill is tightly bound to a particular appointment.  
- **Generalization:** A user can be generalized into patients and doctors.

#### **Composition:**  
Used where one class is a part of another class. E.g., Treatment Plan is composed of multiple prescriptions, which cannot exist independently once the plan is deleted.

---

### **Case Study:**  
This UML class diagram helps stakeholders understand how the Ayurvedic Management System is structured, ensuring clarity in system design, scalability, and efficient communication among team members during software development.

---

### **References:**  
- UML User Guide – Grady Booch  
- Object-Oriented Modeling and Design – Rumbaugh  
- Class Notes and System Design Textbooks  

+----------------------+
|       Patient        |
+----------------------+
| - patientID: int     |
| - name: String       |
| - age: int           |
| - gender: String     |
| - contact: String    |
+----------------------+
| +bookAppointment()   |
| +viewPrescription()  |
+----------------------+

          |
          | 1
          | 
          | * 
+------------------------+
|     Appointment        |
+------------------------+
| - appointmentID: int   |
| - date: Date           |
| - time: String         |
| - doctorID: int        |
+------------------------+
| +schedule()            |
| +cancel()              |
+------------------------+

          |
          | * 
          | 
          | 1
+------------------------+
|        Doctor          |
+------------------------+
| - doctorID: int        |
| - name: String         |
| - specialization: String|
+------------------------+
| +consultPatient()      |
| +writePrescription()   |
+------------------------+

          |
          | 1
          |
          | *
+------------------------+
|     Prescription       |
+------------------------+
| - prescriptionID: int  |
| - date: Date           |
| - medicines: String    |
+------------------------+
| +generateBill()        |
+------------------------+

          |
          | 1
          |
          | *
+------------------------+
|       Medicine         |
+------------------------+
| - medicineID: int      |
| - name: String         |
| - quantity: int        |
| - price: float         |
+------------------------+
| +checkAvailability()   |
| +updateStock()         |
+------------------------+

          |
          | 1
          |
          | *
+------------------------+
|        Billing         |
+------------------------+
| - billID: int          |
| - amount: float        |
| - paymentMode: String  |
+------------------------+
| +generateInvoice()     |
| +processPayment()      |
+------------------------+
