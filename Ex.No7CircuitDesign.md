# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE:                                                                            
### REGISTER NUMBER : 212221040036
### AIM: 
To write a logic program to design a circuit like half adder and half subtractor.
###  Algorithm:
1. Start the Program
2. Design a AND gate logic if both inputs are 1 then output is 1.
3. Design a OR gate logic if any one of input is 1 then output is 1.
4. Design a XOR gate logic if both inputs are different then output is 1.
5. Design a NOT gate logic if input is 0 then output is 1.
6. Design a half adder and half subtractor using the rules.
7. Test the logic.
8. Stop the program.

### Program:
```
and(0,1,0).
and(1,0,0).
and(1,1,1).
or(0,0,0).
or(0,1,1).
or(1,0,1).
or(1,1,1).
xor(0,0,0).
xor(0,1,1).
xor(1,0,1).
xor(1,1,0).
not(0,1).
not(1,0).

halfadder(A,B,Sum,Carry):-
	xor(A,B,Sum),and(A,B,Carry).
fulladder(A,B,C,Sum,Carry):-
	xor(A,B,X),and(A,B,Y),xor(X,C,Sum),and(X,C,Y),or(Y,Z,Carry).
halfsubtractor(A,B,Diff,Borrow):-
	xor(A,B,Diff),not(A,X),and(X,B,Borrow).
fullsubtractor(A,B,C,Diff,Borrow):-
	xor(A,B,X),not(A,M),and(M,B,Y),xor(X,C,Diff),not(X,N),and(N,C,Z),or(Y,Z,Borrow).

```








### Output:
![image](https://github.com/Bhargava-Shankar/AI_Lab_2023-24/assets/85554376/15b45847-0bb0-47a2-865f-91a7f7e25d54)


### Result:
Thus the truth table of circuit verified sucessfully.
