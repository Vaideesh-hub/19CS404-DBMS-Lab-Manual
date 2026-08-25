# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

## PROGRAM:
```
DECLARE
    a NUMBER := 15;
    b NUMBER := 80;
BEGIN
    IF a > b THEN
        DBMS_OUTPUT.PUT_LINE('The greater number is: ' || a);
     ELSIF b > a THEN
        DBMS_OUTPUT.PUT_LINE('The greater number is: ' || b);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Both numbers are equal: ' || a);
    END IF;
END;
/
```
## OUTPUT:


<img width="857" height="320" alt="image" src="https://github.com/user-attachments/assets/2475420a-9260-4444-94e0-527aa471615a" />


**Expected Output:**  
Greater number is: 80

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

### PROGRAM:
```
DECLARE
    n     NUMBER := 10;
    i     NUMBER := 1;
    total NUMBER := 0;
BEGIN
    WHILE i <= n LOOP
        total := total+ i;
        i := i + 1;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || total);
END;
/
```
### OUTPUT:

<img width="892" height="340" alt="image" src="https://github.com/user-attachments/assets/4678e417-13b4-4a21-bc2a-3d2cd856a156" />


**Expected Output:**  
Sum of first 10 natural numbers is: 55

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

### PROGRAM :
```
DECLARE
    n NUMBER := 7;   
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
    i NUMBER := 1;
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci Series up to ' || n || ' terms:');
    IF n >= 1 THEN
        DBMS_OUTPUT.PUT_LINE(a);
    END IF;
    
    IF n >=2 THEN
        DBMS_OUTPUT.PUT_LINE(b);
    END IF;

     i := 3;
    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
END;
/
```

### OUTPUT :

<img width="1085" height="518" alt="image" src="https://github.com/user-attachments/assets/53322fad-9ca0-430c-93b7-287e9f5ddccc" />


**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

### PROGRAM:
```
DECLARE
    n         NUMBER := 1535;
    reversed  NUMBER := 0;
    digit     NUMBER;
    temp      NUMBER;
BEGIN
    temp := n;

    WHILE temp > 0 LOOP
        digit    := MOD(temp, 10);
        reversed := (reversed * 10) + digit;
        temp     := TRUNC(temp / 10);
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Original number: ' || n);
    DBMS_OUTPUT.PUT_LINE('Reversed number: ' || reversed);
END;
/
```

### OUTPUT:

<img width="1032" height="307" alt="image" src="https://github.com/user-attachments/assets/bdcc14ca-7aa5-47be-8ec0-d329ef164b61" />


**Expected Output:**  
n = 1535  
Reversed number is 5351

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

### PROGRAM:
```
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
BEGIN
    IF a >= b AND a >= c THEN
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || a);
    ELSIF b >= a AND b >= c THEN
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || b);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || c);
    END IF;
END;

```

### OUTPUT:

<img width="1117" height="293" alt="image" src="https://github.com/user-attachments/assets/9b1d638c-f1ca-4b45-ab3d-5a36f083b688" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
