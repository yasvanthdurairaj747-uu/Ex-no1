# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations
### AIM
To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.
### APPARATUS REQUIRED
Personal Computer with MASM Software
### 1. ADDITION
#### ALGORITHM

1.Initialize registers and memory.    
2.Load two 16-bit numbers into AX and BX.  
3.Add both numbers.  
4.Check for carry and increment counter if carry occurs.  
5.Store sum in memory.  
6.Store carry in next memory location.  
7.Stop execution.  


#### FLOW CHART
<img width="377" height="522" alt="image" src="https://github.com/user-attachments/assets/bd33a0c3-7a78-4c35-9c80-93dab8bae111" />

#### PROGRAM

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
MOV CL,00H
MOV AX,1234H
MOV BX,1234H
ADD AX,BX
JNC L1
INC CL
L1:MOV SI,1200H
MOV [SI],AX
MOV [SI+02],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### OUTPUT TABLE

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      2000 : 12          |        2004 : 24         |
|      2001 : 34          |        2005 : 68         |  
|      2002 : 12          |        2006 : 00         |
|      2003 : 34          |                          |  


#### MANUAL CALCULATION
![WhatsApp Image 2026-02-09 at 08 19 42](https://github.com/user-attachments/assets/3a6f559e-04a5-462b-a5e2-5ca9ed59c2a3)


---

### OUTPUT IMAGE FROM MASM SOFTWARE
<img width="540" height="300" alt="debug_000" src="https://github.com/user-attachments/assets/3bbca00c-6660-43b1-be90-9012327f1f2c" />

### 2. SUBTRACTION

#### ALGORITHM

1.Initialize registers and memory.  
2.Load two 16-bit numbers into AX and BX.  
3.Subtract the contents of BX from AX.  
4.Check for borrow and increment counter if borrow occurs.  
5.Store the difference in memory.   
6.Store the borrow in the next memory location.  
7.Stop execution.  

#### FLOWCHART

<img width="377" height="484" alt="image" src="https://github.com/user-attachments/assets/fec934e1-7f2b-4b6e-bd8a-2b0b6a80ef52" />

#### PROGRAM
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV AX,1234H
MOV BX,1234H
SUB AX,BX
JNC DOWN
INC CL
DOWN: MOV SI,1200H
MOV [SI],AX
MOV [SI+2],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### OUTPUT TABLE

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      2000 : 12          |        2004 : 00         |
|      2001 : 34          |        2005 : 00         |  
|      2002 : 12          |                          |
|      2003 : 34          |                          |  


#### MANUAL CALCULATION

![sub](https://github.com/user-attachments/assets/ea1b1a4b-0550-4e83-88b5-402f51ca0c83)

---


### OUTPUT SCREEN FROM MASM SOFTWARE
<img width="540" height="300" alt="debug_001" src="https://github.com/user-attachments/assets/ff730153-68b5-4301-a2f2-b78d75d9fa5f" />

### 3. MULTIPLICATION

#### ALGORITHM

1.Initialize registers and memory.  
2.Clear the DX register to store the higher-order result.  
3.Load the first 16-bit number into register AX.  
4.Load the second 16-bit number into register BX.  
5.Multiply the contents of AX and BX.  
6.Store the lower 16-bit result from AX into memory.  
7.Store the higher 16-bit result from DX into the next memory location.  
8.Stop execution.  

#### FLOWCHART

<img width="323" height="539" alt="image" src="https://github.com/user-attachments/assets/6f111bbb-d1b2-4723-8f1d-a6b88d011a79" />


#### PROGRAM

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV DX,0000H
MOV AX,1234H
MOV BX,1234H
MUL BX
MOV SI,1200H
L1: MOV[SI],AX
MOV [SI+02H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### OUTPUT TABLE

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      2000 : 12          |        2004 : 90         |
|      2001 : 34          |        2005 : 5A         |  
|      2002 : 12          |        2006 : 4B         |
|      2003 : 34          |        2007 : 01         | 

#### MANUAL CALCULATION

![mul](https://github.com/user-attachments/assets/c7c35a76-5153-43cd-bfec-d4bbf53f6f32)


---

### OUTPUT SCREEN FROM MASM SOFTWARE
<img width="540" height="300" alt="debug_002" src="https://github.com/user-attachments/assets/7e96f009-f4ea-450c-b76f-f6841372e3e4" />

### 4. DIVISION

#### ALGORITHM

1.Initialize registers and memory.  
2.Clear the DX register.  
3.Load the dividend into AX and the divisor into BX.  
4.Divide the contents of AX by BX.  
5.Store the quotient in AX and the remainder in DX.  
6.Store the quotient in memory.  
7.Store the remainder in the next memory location.  
8.Stop execution.  

#### FLOWCHART
<img width="255" height="280" alt="image" src="https://github.com/user-attachments/assets/b96a307e-4799-485f-a28f-20f2a5dbe3b1" />

#### PROGRAM

```asm
CODE SEGMENT
ASSUME CS:CODE,DS:CODE
ORG 1000H
MOV DX,0000H
MOV AX,1234H
MOV BX,1234H
DIV BX
MOV SI,1200H
MOV [SI],AX
MOV [SI+02H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### OUTPUT TABLE

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       2000 : 12          |        2004 : 01         |
|       2001 : 34          |        2005 : 00         |  
|       2002 : 12          |        2006 : 00         |
|       2003 : 34          |        2007 : 00         |  



#### MANUAL CALCULATION
![div](https://github.com/user-attachments/assets/f827826f-6f5a-42e8-b07c-7061d23c641a)

### OUTPUT FROM MASM SOFTWARE
<img width="540" height="300" alt="debug_003" src="https://github.com/user-attachments/assets/a17eb401-a191-46d1-bec8-86c19aa0b160" />

### RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.
