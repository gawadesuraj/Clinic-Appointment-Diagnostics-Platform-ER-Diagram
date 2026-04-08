# Clinic Appointment & Diagnostics Platform - ER Diagram

## Overview

This project contains the Entity Relationship Diagram (ERD) for a clinic appointment and diagnostics platform. The system is designed to manage doctors, patients, appointments, consultations, diagnostic tests, reports, and payments in a structured and scalable way.

The clinic workflow:
Patient → Appointment → Consultation → Diagnostic Tests → Reports → Payment

---

## Features Covered

* Patient management
* Doctor & specialty management
* Appointment booking
* Consultation tracking
* Diagnostic test prescriptions
* Report generation
* Multiple tests per consultation
* Patient visit history
* Payment tracking
* Clean normalized database design

---

## Entities

### Patients

* patient_id (PK)
* name
* phone
* email
* gender
* date_of_birth
* address
* created_at

---

### Specialties

* specialty_id (PK)
* specialty_name

---

### Doctors

* doctor_id (PK)
* name
* phone
* email
* specialty_id (FK)

---

### Appointments

* appointment_id (PK)
* patient_id (FK)
* doctor_id (FK)
* appointment_date
* status
* reason

---

### Consultations

* consultation_id (PK)
* appointment_id (FK)
* patient_id (FK)
* doctor_id (FK)
* diagnosis
* notes
* consultation_date

---

### Tests

* test_id (PK)
* test_name
* description
* price

---

### Consultation Tests

* consultation_test_id (PK)
* consultation_id (FK)
* test_id (FK)
* status

---

### Reports

* report_id (PK)
* consultation_test_id (FK)
* report_url
* result_summary
* generated_at

---

### Payments

* payment_id (PK)
* patient_id (FK)
* appointment_id (FK)
* amount
* payment_status
* payment_method
* paid_at

---

## Relationships

* One patient can book many appointments
* One doctor can attend many appointments
* One appointment may lead to one consultation
* One consultation can have multiple tests
* Each test generates a report
* Payments linked to appointments
* Doctors belong to specialties

---

## Files

* `clinic-erd.txt` → ER diagram code
* `diagram.png` → exported ER diagram
* `README.md` → documentation

---

## Assignment

Web Dev Cohort 2026
Database Design - Clinic Appointment & Diagnostics Platform
