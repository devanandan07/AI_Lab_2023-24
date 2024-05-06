# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE: 30/3/24                                                                           
### REGISTER NUMBER : 212221040036
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
```
likes (john,X):-
food(X).
eats(bill,X):-
eats(sue,X).
eats (Y,X):-
food(X).
eats (bill, peanuts).
food(apple).
food(chicken).
food(peanuts).
```


### Output:
![image](https://github.com/Bhargava-Shankar/AI_Lab_2023-24/assets/85554376/71ee7883-4451-4afd-9eda-b8fa8cc320cb)


### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
```
likes (steve, X):- easycourse (X). 
hard (sciencecourse). 
easycourse(X):- course (X, dept (havefun)). 
course (bk301, dept(havefun)).
```


### Output:
![image](https://github.com/Bhargava-Shankar/AI_Lab_2023-24/assets/85554376/7f689ec9-b508-47f4-8ffb-54d74b3fa240)


### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program
```
criminal(X):-american (X), weapon (Y), hostile (Z), sells(X, Y, Z).
weapon (Y):-missile(Y).
hostile(Z):-enemy (Z,X).
sells (west, Y, nano):-missile (Y), owns (nano, Y), missile(m).
owns (nano, m).
enemy(nano, america).
american(west).
```

### Output:
![image](https://github.com/Bhargava-Shankar/AI_Lab_2023-24/assets/85554376/0d66a55e-b3b2-4691-b506-4c7c9df8a9b0)


### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
