# 🏥 Hospital Appointment & Triage System
### Capstone Assignment – Data Structures (Python Implementation)

This project implements a **console-based Hospital OPD Management System** focused on Data Structures.  
It simulates real-world hospital workflows: patient registration, doctor schedules, appointment queues, emergency triage, and undo operations.

The system integrates **multiple data structures**:
- Circular Queue  
- Min Heap (Priority Queue)  
- Singly Linked List  
- Stack (Undo Log)  
- Hash Table (Patient Index)

---

## 📌 Features Implemented

### ✅ 1. **Doctor Schedule Management (Linked List)**
Each doctor has a linked list of:
- `slotId`
- `startTime`
- `endTime`
- `status` (AVAILABLE / BOOKED / CANCELLED)

Supports:
- Add Slot  
- Cancel Slot  
- Traverse Schedule  

### ✅ 2. **Routine Appointment Queue (Circular Queue)**
Used for normal OPD appointments.
- `enqueueRoutine(token)`
- `dequeueRoutine()`
- Overflow & underflow handled

### ✅ 3. **Emergency Triage (Min Heap / Priority Queue)**
Emergency patients are prioritized based on:
Implements:
- Insert emergency case  
- Extract-min (highest priority)  
- Preemption over routine queue  

### ✅ 4. **Patient Index (Hash Table with Chaining)**
Stores:
- patientId  
- name  
- age  
- severity  
- visit history  

Supports CRUD:
- insert
- get
- update
- delete

### ✅ 5. **Undo System (Stack)**
Every update is logged as an `UndoAction` with:
- `action_type`
- `payload`
- `revert_fn()`

Supports:
- Undo last operation safely  
- Rollback queue changes, patient updates, slot changes, etc.

### ✅ 6. **Reports**
- Per doctor pending count  
- Served vs pending summary  
- Top-K most frequent patients  

---

## 🧮 Data Structures Used

| Feature | Data Structure | Why |
|--------|----------------|-----|
| Routine Appointments | Circular Queue | O(1) enqueue/dequeue |
| Emergency Triage | Min Heap | O(log n) insert/pop with priority |
| Doctor Schedule | Singly Linked List | Dynamic slot additions |
| Undo System | Stack | LIFO rollback |
| Patient Index | Hash Table (Chaining) | Fast O(1) average CRUD |

---

## 🧠 Time & Space Complexity (Highlights)

| Operation | Complexity |
|----------|------------|
| Queue Enqueue / Dequeue | **O(1)** |
| Heap Insert / Extract | **O(log n)** |
| Hash Table Search | **O(1)** Avg |
| Linked List Insert | **O(1)** |
| Undo Push/Pop | **O(1)** |

---

## 📂 Project Structure


Inside `hospital_system.py`:
- `Patient`
- `Doctor`
- `Token`
- `CircularQueue`
- `EmergencyQueue`
- `HashTable`
- `UndoStack`
- `HospitalSystem`
- `demo()` test function

---

## ▶️ Running the Demo

```bash
python3 hospital_system.py
