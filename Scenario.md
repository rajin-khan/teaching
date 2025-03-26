### **Scenario-Based Question (Example 1)**  (12)
A charity organization is creating a software system to manage donations and send thank-you messages to donors.

Write a pseudocode algorithm that:
- Inputs the names and donation amounts for 100 donors.
- Stores the donor names and amounts in parallel arrays.
- Calculates the total donation amount.
- Outputs the name(s) of the donor(s) who donated the highest amount and the total amount donated.

You may assume that:
- All donations are positive real numbers.
- No two donors have the same name.

---

### **Mark Scheme (Example 1 Answer)**

**(a) Declare arrays and variables [2]**
- `DECLARE DonorNames : ARRAY[1:100] OF STRING` (1)
- `DECLARE Donations : ARRAY[1:100] OF REAL` (1)

**(b) Input loop [3]**
- `FOR Index ← 1 TO 100` (1)
- `    INPUT DonorNames[Index]` (1)
- `    INPUT Donations[Index]` (1)
- `NEXT Index`

**(c) Calculate total and find highest donation [4]**
- `Total ← 0` (1)
- `Max ← Donations[1]` (1)
- `FOR Index ← 1 TO 100`  
- `    Total ← Total + Donations[Index]` (1)  
- `    IF Donations[Index] > Max THEN`  
- `        Max ← Donations[Index]`  
- `    ENDIF`  
- `NEXT Index` (1)

**(d) Output total and highest donor(s) [3]**
- `OUTPUT "Total amount donated is ", Total` (1)
- `FOR Index ← 1 TO 100`  
- `    IF Donations[Index] = Max THEN`  
- `        OUTPUT "Top donor: ", DonorNames[Index]` (1)  
- `    ENDIF`  
- `NEXT Index` (1)

**Total: 12 Marks**

---
