# Software-Engineering-Project
<p align="center">
  <img src="https://img.shields.io/badge/Language-C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++"/>
  <img src="https://img.shields.io/badge/IDE-Dev--C++-2C2D72?style=for-the-badge&logo=cplusplus&logoColor=white" alt="Dev-C++"/>
  <img src="https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows"/>
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge" alt="Status"/>
</p>

# 🅿️ Parking Lot Management System

> A smart, console-based parking management solution built in **C++** using **Data Structures & Algorithms (DSA)** — designed to automate vehicle entry, slot allocation, license verification, and exit processing in real time.

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [System Architecture](#-system-architecture)
- [Data Structures Used](#-data-structures-used)
- [Software Development Model](#-software-development-model)
- [System Requirements](#-system-requirements)
- [Getting Started](#-getting-started)
- [Menu Options](#-menu-options)
- [Test Cases](#-test-cases)
- [UML Diagrams](#-uml-diagrams)
- [Future Enhancements](#-future-enhancements)
- [Team Members](#-team-members)

---

## 📖 About the Project

The **Parking Lot Management System** is a C++ console application that replaces traditional manual parking record-keeping with a fully automated, memory-efficient digital solution. The system digitally records vehicle entries and exits, dynamically allocates parking slots, and verifies vehicle legality against predefined data.

Upon entry, the system scans each vehicle, detects the number of passengers, verifies license plate authenticity, and assigns an available parking slot — all powered by core DSA concepts including **Linked Lists**, **Queues**, and **Arrays**.

### 🎯 Purpose

- Replace manual record-keeping with a computerized, efficient process
- Collect and store vehicle details *(owner name, vehicle type, license plate, entry time)*
- Identify illegal or stolen vehicles through stored verification data
- Ensure fair slot utilization with accurate digital records

---

## ✨ Features

| Feature                              | Description                                                                                      |
| ------------------------------------ | ------------------------------------------------------------------------------------------------ |
| **🚗 Add Vehicle**             | Records vehicle details (owner name, license plate, type, passengers) and assigns a parking slot |
| **🔍 Scan Vehicle**            | Simulates vehicle scanning to detect passengers and verify license validity                      |
| **🚪 Remove Vehicle**          | Deletes vehicle record on exit and displays the exit timestamp                                   |
| **📋 Display Parked Vehicles** | Shows a complete list of all currently parked vehicles with details                              |
| **🔐 License Verification**    | Cross-checks license plates against a predefined list of illegal/stolen entries                  |
| **📊 Parking Summary**         | Displays total, occupied, and available parking slots in real time                               |

---

## 🏗️ System Architecture

```
┌──────────────────────────────────────────────────┐
│                   MAIN MENU                      │
│  ┌────────────────────────────────────────────┐  │
│  │  1. Add Vehicle    │  2. Remove Vehicle    │  │
│  │  3. Display All    │  4. Check License     │  │
│  │  5. Parking Summary│  6. Exit              │  │
│  └────────────────────────────────────────────┘  │
└──────────────────────┬───────────────────────────┘
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
  ┌──────────┐  ┌──────────┐  ┌──────────────┐
  │  Linked  │  │  Queue   │  │    Array      │
  │   List   │  │ (Slots)  │  │ (Illegal DB) │
  │(Vehicles)│  │          │  │              │
  └──────────┘  └──────────┘  └──────────────┘
```

---

## 🧮 Data Structures Used

| Data Structure        | Purpose                                                                                                       |
| --------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Linked List** | Dynamic storage for vehicle records — allows efficient insertion and deletion without fixed size limitations |
| **Queue**       | Manages parking slot allocation logically, ensuring orderly assignment and release                            |
| **Array**       | Stores predefined illegal/stolen license plates for quick verification lookups                                |

---

## 🔄 Software Development Model

This project was developed using the **Incremental Model**, where each module was built and tested independently before integration:

```
Increment 1 ──► Vehicle Data Structure (Linked List)
Increment 2 ──► Vehicle Entry & Exit Functionality
Increment 3 ──► License Verification & Passenger Detection
Increment 4 ──► Display & Summary Features (Final Integration)
```

**Why Incremental?**

- ✅ Stepwise development with verified modules
- ✅ Early working prototype available
- ✅ Easy debugging in isolated increments
- ✅ Scalable for future modules

---

## 💻 System Requirements

| Requirement         | Specification                                            |
| ------------------- | -------------------------------------------------------- |
| **Language**  | C++                                                      |
| **IDE**       | Dev-C++ (or any C++ compiler)                            |
| **Platform**  | Windows 10 or later                                      |
| **Libraries** | `<iostream>`, `<string>`, `<ctime>`, `<cstdlib>` |
| **Capacity**  | Up to 10 vehicles (configurable)                         |

---

## 🚀 Getting Started

### Prerequisites

- [Dev-C++](https://sourceforge.net/projects/orwelldevcpp/) or any standard C++ compiler (g++, MinGW, etc.)

### Installation & Run

1. **Clone the repository**

   ```bash
   git clone https://github.com/Zaneera-05/parking-lot-management-system.git
   cd parking-lot-management-system
   ```
2. **Open in Dev-C++**

   - Launch Dev-C++
   - Go to `File → Open` and select the `.cpp` source file
3. **Compile & Run**

   - Press `F11` to compile and run
   - **Or** compile via terminal:
     ```bash
     g++ -o parking main.cpp
     ./parking
     ```
4. **Navigate the menu** using number keys `1-6`

---

## 📌 Menu Options

```
╔═══════════════════════════════════════╗
║   PARKING LOT MANAGEMENT SYSTEM      ║
╠═══════════════════════════════════════╣
║   1. Add Vehicle                      ║
║   2. Remove Vehicle                   ║
║   3. Display Parked Vehicles          ║
║   4. Check License Plate              ║
║   5. Show Parking Summary             ║
║   6. Exit                             ║
╚═══════════════════════════════════════╝
```

### Option Details

- **Add Vehicle** → Enter owner name, license plate, and vehicle type. The system auto-generates passenger count (1–5), verifies legality, and assigns a slot.
- **Remove Vehicle** → Enter the license plate of the exiting vehicle. The system frees the slot and displays the exit timestamp.
- **Display Parked Vehicles** → View all vehicles currently parked with their complete details.
- **Check License Plate** → Verify whether a specific license plate is legal or flagged as stolen/illegal.
- **Parking Summary** → View total slots, occupied slots, and available slots at a glance.

---

## ✅ Test Cases

All **7 test cases** passed successfully with no major issues found during testing:

| #  | Test Case                      | Input                       | Expected Result                  | Status  |
| -- | ------------------------------ | --------------------------- | -------------------------------- | ------- |
| 01 | Add Vehicle — Valid Input     | Valid owner, plate, type    | Vehicle added, slot assigned     | ✅ Pass |
| 02 | Add Vehicle — Illegal License | Plate from illegal list     | Warning displayed, entry blocked | ✅ Pass |
| 03 | Add Vehicle — Parking Full    | Add when all slots occupied | "Parking Full" message           | ✅ Pass |
| 04 | Remove Vehicle — Valid Plate  | Existing plate number       | Vehicle removed, exit time shown | ✅ Pass |
| 05 | Remove Vehicle — Not Found    | Non-existent plate          | "Not Found" message              | ✅ Pass |
| 06 | Display Parked Vehicles        | —                          | All parked vehicles listed       | ✅ Pass |
| 07 | Parking Summary                | —                          | Correct slot statistics          | ✅ Pass |

---

## 📐 UML Diagrams

The project includes the following UML diagrams (available in the project documentation):

- **Use Case Diagram** — Illustrates actor interactions with the system
- **Sequence Diagram** — Shows the flow of operations for vehicle management
- **Activity Diagram** — Maps the workflow from entry to exit
- **Class Diagram** — Defines the `Vehicle` and `ParkingManager` class structures
- **ER Diagram** — Represents entity relationships in the system

---

## 🔮 Future Enhancements

- [ ] **Graphical User Interface (GUI)** — Front-end interface for user-friendly interaction
- [ ] **Database Integration** — Persistent storage using MySQL/SQLite
- [ ] **Payment & Ticketing Module** — Automated fee calculation and receipt generation
- [ ] **Hardware Integration** — Camera/sensor-based vehicle detection (IoT)
- [ ] **File I/O Support** — Save and load parking data across sessions
- [ ] **Multi-level Parking** — Support for multi-floor parking structures

---

## 👥 Team Members

| Name                           | SAP ID | Program | Email                 | Responsibilities                                                                                                                |
| ------------------------------ | ------ | ------- | --------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| **Aina Mahboob**         | 63935  | BSSE    | mahadktk405@gmail.com | Requirements gathering, vehicle data structure design, linked list operations (insertion/deletion), system accuracy testing     |
| **Zara Rani**            | 65543  | BSSE    | zararani133@gmail.com | Slot allocation logic, legality verification (arrays & queues), scanning functionality testing, documentation & flow diagrams   |
| **Zaneera Bint-e-Zahid** | 65326  | BSSE    | zbz201105@outlook.com | Main menu interface, system module integration, license verification, vehicle scanning, summary display, final testing & report |

---

<p align="center">
  <b>⭐ If you found this project helpful, please give it a star! ⭐</b>
</p>
