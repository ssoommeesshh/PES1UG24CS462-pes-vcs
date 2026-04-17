# Version Control System Orange Problem Report

## Course: Operating Systems 

## Name: Somesh Sudhan S

## SRN: PES1UG24CS462

## Section: 4H

---

# 🔹 Phase 1: Object Storage Foundation

## 📸 Screenshot 1A: Test Objects Output

<img width="1461" height="297" alt="image" src="https://github.com/user-attachments/assets/1435550c-fc93-4c0b-8432-545723402dbe" />


---

## 📸 Screenshot 1B: Object Store Structure

<img width="1464" height="258" alt="image" src="https://github.com/user-attachments/assets/78aeec15-a7ab-4d25-934b-263a6c378f6a" />


---

# 🔹 Phase 2: Tree Objects

## 📸 Screenshot 2A: Tree Test Output

<img width="1461" height="227" alt="image" src="https://github.com/user-attachments/assets/a2b8a544-45eb-4710-a731-a7203641526b" />


---

## 📸 Screenshot 2B: Raw Tree Object (xxd)

(Note : used a temprary .c file to upload object into the tree as requirements for the acctual code come later, this was done just to show this output)

<img width="1468" height="315" alt="image" src="https://github.com/user-attachments/assets/db8cb8a2-1422-4d07-9e40-f2c02d8dcb9e" />


---

# 🔹 Phase 3: Index (Staging Area)

## 📸 Screenshot 3A: pes init → add → status

<img width="1028" height="629" alt="image" src="https://github.com/user-attachments/assets/8573b833-0e43-4258-8ddb-90ca263d220f" />


---

## 📸 Screenshot 3B: Index File Contents


<img width="1289" height="169" alt="image" src="https://github.com/user-attachments/assets/98ad3c32-5791-4ab1-b629-62648f453057" />


---

# 🔹 Phase 4: Commits and History

## 📸 Screenshot 4A: pes log Output


<img width="962" height="672" alt="image" src="https://github.com/user-attachments/assets/ac917c0d-14da-4a9d-b121-e8e74e246758" />


---

## 📸 Screenshot 4B: Object Store Growth


<img width="968" height="361" alt="image" src="https://github.com/user-attachments/assets/cc94173f-7058-4102-95f2-1697f9cac10e" />


---

## 📸 Screenshot 4C: HEAD and Branch Reference


<img width="960" height="359" alt="image" src="https://github.com/user-attachments/assets/80b685cf-9871-4f45-8003-9d5b4acb233d" />


---

# 🔹 Final Integration Test

## 📸 Screenshot: Integration Test Output

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/3cfe77d1-0bbf-41d0-9905-3f2b81f449af" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/74698ead-a5cb-45a2-a014-9c8ef90c911d" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/9aa5caa5-e878-481c-8ed9-f1327753b333" />




---

# 🔹 Phase 5: Branching and Checkout (Analysis)

## Q5.1

**Answer:**
A branch is just a file storing a commit hash.
Checkout changes HEAD to point to that branch and updates files in the working directory.
It is complex because files may differ and conflicts can happen.

---

## Q5.2

**Answer:**
Compare index with working directory to detect changes.
If a tracked file is modified and differs from target branch then conflict exists.
In that case checkout should stop to avoid data loss.


---

## Q5.3

**Answer:**
In detached HEAD commits are not linked to any branch.
New commits can be lost if not referenced later.
User can recover them using commit hash or reflog.

---

# 🔹 Phase 6: Garbage Collection (Analysis)

## Q6.1

**Answer:**
Start from all branch heads and mark reachable objects.
Traverse commits trees and blobs using a set or hash table.
Delete objects that are not marked reachable.

---

## Q6.2

**Answer:**
If GC runs during commit it may delete objects still being written.
This creates a race condition and corrupts repository state.
Git avoids this using locks and safe timing for garbage collection.

---

