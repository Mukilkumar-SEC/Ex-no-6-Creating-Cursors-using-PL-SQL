# Ex. No: 6 Creating Cursors using PL/SQL

### AIM:
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```
CREATE TABLE exp6 (
  regno NUMBER,
  name VARCHAR(10),
  dept VARCHAR(10),
  marks NUMBER
);
INSERT INTO exp6 VALUES (1, 'MUKESH', 'AIDS', 10);
INSERT INTO exp6 VALUES (2, 'DARIO', 'AIDS', 12);

```
### PLSQL Cursor code
```

DECLARE
   CURSOR exp6_cursor IS
   SELECT regno,name,dept,marks
   FROM exp6;
   exp6_id NUMBER;
   exp6_name VARCHAR(50);
   exp6_dept VARCHAR(50);
   exp6_salary NUMBER;
BEGIN
  OPEN exp6_cursor;

  LOOP
    FETCH exp6_cursor INTO exp6_id, exp6_name, exp6_dept, exp6_salary;

    EXIT WHEN exp6_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('STUDENT ID: ' || exp6_id);
    DBMS_OUTPUT.PUT_LINE('STUDENT Name: ' || exp6_name);
    DBMS_OUTPUT.PUT_LINE('DEPT: ' || exp6_dept);
    DBMS_OUTPUT.PUT_LINE('MARKS: ' || exp6_salary);
  END LOOP;

  CLOSE exp6_cursor;
END;
/

```
## Output:
#![Screenshot 2023-10-11 012511](https://github.com/Mukilkumar-SEC/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119559663/9eb4553e-ee6e-43cd-a45a-9c0146e5356f)

### Result:
Thus this program executed successfully.
