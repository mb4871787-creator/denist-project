# Dental Clinic Management System — Java / JavaFX

A fully functional desktop application for managing a dental clinic, built with **Java** and **JavaFX**. The system supports three distinct user roles — Doctor, Nurse, and Patient — each with their own dedicated dashboard and feature set. Developed as a university Object-Oriented Programming project.

---

## Screenshots

> *(Add screenshots of the Login screen, Doctor dashboard, and Patient dashboard here)*

---

## Features

### 👤 Role-Based Access Control
| Role | Access |
|------|--------|
| Doctor | Manage appointments, write prescriptions, view patients |
| Nurse | Manage appointments, assist patient records |
| Patient | Book appointments, view prescriptions, make payments |

### 📅 Appointment Management
- Schedule appointments with available doctors by date and time slot
- 10 predefined time slots from 9:00 AM to 7:00 PM
- Appointment status tracking: `SCHEDULED`, `COMPLETED`, `CANCELLED`
- Conflict detection to prevent double-booking

### 💊 Prescription System
- Doctors can issue prescriptions linked to specific appointments
- Each prescription tied to a patient, doctor, and appointment ID
- Prescription history viewable per patient

### 💳 Payment & Billing
- Payment processing linked to appointments
- Support for multiple payment methods (Cash, Card, etc.)
- Patient balance tracking with payment history
- Formatted payment IDs (e.g., `PAY-2025-12-001`)

### 🏥 Clinic Data Management
- Singleton `ClinicManager` acts as the central data store
- Manages all patients, doctors, nurses, appointments, payments, and prescriptions
- Auto-ID generation for all entities (`DOC001`, `PAT001`, `APT-2025-12-001`, etc.)

### 🦷 Doctor Specializations
`General Dentistry` · `Orthodontics` · `Periodontics` · `Endodontics` · `Prosthodontics` · `Pediatric Dentistry` · `Oral Surgery` · `Other`

---

## Architecture & OOP Concepts

```
src/
└── Java/
    ├── App/
    │   └── App.java              # JavaFX entry point, loads LoginView
    ├── Models/
    │   ├── Person.java           # Abstract base class (inheritance)
    │   ├── Doctor.java           # Extends Person, implements Comparable
    │   ├── Patient.java          # Extends Person, implements Comparable
    │   ├── Nurse.java            # Extends Person
    │   ├── Appointment.java      # Booking entity with slot & status
    │   ├── Payment.java          # Implements Payable interface
    │   ├── Prescription.java     # Linked to appointment + patient
    │   ├── ClinicManager.java    # Singleton - central business logic
    │   ├── Payable.java          # Interface for payment processing
    │   ├── AppointmentSlot.java  # Enum: 10 time slots
    │   ├── AppointmentStatus.java# Enum: SCHEDULED / COMPLETED / CANCELLED
    │   ├── Specialization.java   # Enum: 8 dental specializations
    │   ├── Gender.java           # Enum
    │   ├── UserRole.java         # Enum: DOCTOR / NURSE / PATIENT
    │   ├── PrescriptionItem.java # Drug/dosage details
    │   └── PaymentMethod.java    # Enum: CASH / CARD / etc.
    ├── Views/
    │   ├── Dashboards/           # Login + role dashboards (FXML)
    │   ├── Doctor/               # Doctor-specific views
    │   ├── Nurse/                # Nurse-specific views
    │   └── Patient/              # Patient-specific views
    └── Controllers/
        ├── Dashboards/           # Login & routing controllers
        ├── Doctor/               # Doctor action controllers
        ├── Nurse/                # Nurse action controllers
        └── Patient/              # Patient action controllers
```

**Key OOP principles demonstrated:**
- **Inheritance** — `Doctor`, `Patient`, `Nurse` all extend `Person`
- **Abstraction** — `Person` is an abstract class; `Payable` is an interface
- **Encapsulation** — all fields are private with controlled getters/setters
- **Polymorphism** — `Comparable<T>` implemented on Doctor, Patient, Appointment for sorting
- **Singleton pattern** — `ClinicManager.getInstance()` manages shared state
- **MVC architecture** — FXML views separated from Java controllers

---

## Tech Stack

| Technology | Purpose |
|------------|---------|
| Java 17+ | Core language |
| JavaFX | GUI framework (FXML + Scene Builder) |
| IntelliJ IDEA | IDE |
| JUnit Jupiter | Unit testing |

---

## Getting Started

### Prerequisites
- Java 17 or higher
- JavaFX SDK (if not bundled with your JDK)
- IntelliJ IDEA (recommended) or any Java IDE

### Run the Project

1. Clone the repository:
```bash
git clone https://github.com/mb4871787-creator/dental-clinic-management.git
cd dental-clinic-management
```

2. Open in IntelliJ IDEA → **File > Open** → select the `Dentist` folder

3. Make sure JavaFX is configured in your project libraries

4. Run `App.java`

### Default Login Credentials

| Role | Username | Password |
|------|----------|----------|
| Doctor | `doc1` | `dpass1` |
| Doctor | `doc2` | `dpass2` |
| Nurse | `baiomy` | `baiomy` |
| Patient | `pat1` | `ppass1` |
| Patient | `pat2` | `ppass2` |

---

## Author

**Mohamed Baiomy Abdelkader**  
Mechatronics & Robotics Engineering Student — Ain Shams University  
[LinkedIn](https://linkedin.com/in/mohamed-baiomy) · [GitHub](https://github.com/mb4871787-creator)
