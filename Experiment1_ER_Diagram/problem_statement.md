# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
Hospital

## ER Diagram:
The ER diagram models a hospital system with entities for patients, doctors, hospitals, and medical records.
![image](https://github.com/user-attachments/assets/9af55308-9406-42c9-afeb-6d47563a2306)

## Entities and Attributes:
- HOSPITAL
Hospital_Id,Hospital_Name,Hospital_Address,Hospital_City

- PATIENT
Patient_Id,Patient_Name,Patient_Address,Patient_Diagnosis

- DOCTOR
Doctor_Id,Doctor_Name,Qualification,Salary

- MEDICAL RECORD
Record_Id,Date_of_Examination,Problem


## Relationships and Constraints:
- PATIENT — Admitted in —> HOSPITAL
Cardinality: Many-to-One (Many patients can be admitted in one hospital)
Participation: Total on Patient side (Each patient must be admitted to a hospital)

- HOSPITAL — Has —> DOCTOR
Cardinality: One-to-Many (A hospital can have many doctors)
Participation: Total on Hospital side (Every hospital must have doctors)

- PATIENT — Has —> MEDICAL RECORD
Cardinality: One-to-Many (A patient can have many medical records)
Participation: Total on Patient side (Every medical record must be linked to a patient)


## Extension (Diagnosis):
-The Patient Diagnosis attribute in the PATIENT entity captures the essential medical condition for which the patient is treated. Billing details are not explicitly modeled here but can be extended with an additional entity Billing linked to Patient and Medical Record.
## Design Choices:
Entities like Patient, Doctor, Hospital, and Medical Record reflect real-world medical data management needs.
Relationships were chosen to represent realistic interactions like admissions and treatment histories.
Medical Record is separated as an entity to allow detailed tracking of each consultation or diagnosis.
Total Participation is used where relationships are mandatory for data integrity, like patients requiring hospital assignment and having at least one medical record.



## RESULT
Thus the ER daigram have been successfully drawn and explained briefly.
