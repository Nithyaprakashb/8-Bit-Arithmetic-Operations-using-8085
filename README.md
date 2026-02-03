
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:

### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:
```
CMC
LDA 4200H
MOV B, A
LDA 4201H
ADD B
STA 4300H
HLT
```

### Output:
<img width="1861" height="1006" alt="image" src="https://github.com/user-attachments/assets/ad26084e-032b-4a2a-b6a8-f880d5e6cbee" />
<img width="305" height="499" alt="image" src="https://github.com/user-attachments/assets/c63bcb85-d147-4b44-9d5c-f8ff7f67e1d8" />




[ADDITION EXPLANTION].<img width="1583" height="1599" alt="image" src="https://github.com/user-attachments/assets/41d1983a-f2b0-4185-a896-321b4304c711" />



### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
```
LDA 4200H
MOV C, A
LDA 4201H
CMP C
MOV B, A
MOV A, C
SWAP:
SUB B
STA 4300H
HLT
```

### Output:
<img width="313" height="401" alt="image" src="https://github.com/user-attachments/assets/d721ebc1-2053-46ed-b670-9b701f5680e2" />
<img width="305" height="418" alt="image" src="https://github.com/user-attachments/assets/e224f929-e3e5-4cc8-bdeb-a446d54f7f53" />
<img width="1213" height="517" alt="image" src="https://github.com/user-attachments/assets/54ea3cfd-4474-43a6-8cff-26e0970fbc0c" />


[SUBTRACTION EXPLANTION].<img width="1600" height="994" alt="image" src="https://github.com/user-attachments/assets/4a691638-d2b2-47ce-a3a8-fe85c03d6a9d" />




### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
```
LDA 4200H
MOV C, A
LDA 4201H
MOV B, A
MVI A, 00H
LOOP: ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
```

### Output:
<img width="299" height="392" alt="image" src="https://github.com/user-attachments/assets/c279f4c8-3160-4a47-9193-ad1a6c39f160" />

<img width="306" height="431" alt="image" src="https://github.com/user-attachments/assets/f1c598c8-9c2f-4e3b-843f-a71ef9c3039f" />
<img width="924" height="490" alt="image" src="https://github.com/user-attachments/assets/9fdb01a6-6965-484b-a37c-1e861632f269" />



[MULTIPLICTION EXPLANATION1]<img width="1600" height="1181" alt="image" src="https://github.com/user-attachments/assets/1474c315-a9b5-4f46-9652-ce4f1ad7cf1d" />

### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:
```
LDA 4200H
MOV C,A
LDA 4201H
MOV B,A
MVI A,00H
LOOP: MOV A,C
CMP B
JC END
SUB B
MOV C,A
INR D
JMP LOOP
END: MOV A,D
STA 4300H
MOV A,C
STA 4301H
HLT
```

### Output:
<img width="303" height="434" alt="image" src="https://github.com/user-attachments/assets/d72d48b6-407d-4738-bed8-291ac026be40" />

![Uploading image.png…]()

[DIVISION EXPLANATION].<img width="1322" height="1030" alt="image" src="https://github.com/user-attachments/assets/e169f664-e6c4-4e01-8fba-36a303514825" />





## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

