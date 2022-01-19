# CoreCode

- [Tuesday](#week-1-tuesday-challenges)
- [Wednesday](#week-1-wednesday-challenges)
- [Thursday](#week-1-thursday-challenges)


## Week 1 Tuesday Challenges
### Java language is compiled or interpreted? 
It is both, the code is first compiled into bycode that the Java Runtime Enviroment(JRE) can understand, and then this bycode is interpreted by the Java Virtual Machine(JVM). The use of bycode makes the intepretation much quicker.
### Create an algorithm to calculate the equivalent of your local currencty to USD
Enter value in El Salvador color currency
Multiple entered value by 0.1142
Print result in USD.
```

sv = input("Enter amount in colones: ")
usd = int(sv) * (0.1142)
print("The amount in US dollar is: " + str(usd))

```
### Why is pseudocode helpful?
It allows you to organize your ideas and to decide how the code will actually work, by just adding the steps to it. It helps understand how the code will work or what the code will do without having to actually write it.
### Pseudo code to calculate age based on year. 
1- Define variable 'year' equal input, input will ask for the year they were born
2- Define varibale 'age'  equal to  2022 - variable 'year'
3- Print 'age' with the result
### Why are flowcharts important to us as developers?
Flowcharts are useful to demostrate the logic behind a program, it is also helpful when creating a new program, so it can be use to find the correct proces to follow or how the program should work before coding it. It is similar to pseudo code as it provides an idea and logic to the code without havint to actual code, but in an a graphic form easier to understand to non coders.
### High-level languages and Low-level languages
High-Level languages are languages that are easier for the programmer to understand, but not so much for the computer, this lenguajes are the ones we normally use to code that need to be compiled or interpreted first. 
Low-level languages are the ones easier for computers to understand like 0s and 1s and example of this are Assemmbly languages.

## Week 1 Wednesday Challenges
### Learn about binary, decimal and hexadecimal numbers.
Binary is a numeral system based on ones and zeros that can be understood by computers as they represent on and off operations. 
Decimal is a numeral system easier for people to understand and standard in most langauges they go from 0 to 9 and have something called places. a number 3 in a 10th place is 30.
Hexadecimal number is based 16 meaning there are 16 different digits they go from 0 to 9 for numeral and then they use A,B,C,D,E,F. For the rest of the values.  It’s used primarily as a convenient way to represent binary values for human operators. A single place value in hexadecimal represents four bits of memory. That means two places represents eight bits, or one byte.

### Translate the year you where born to binary, decimal and hexadecimal
Binary = 11111000100
Decimal = 1988
Hexadecimal = 0x7C4

### Translate 51966 into hexadecimal and binary
Bynary = 1100101011111110
Hexadecimal = 0xCAFE

### Create a program to add two numbers given by the user
```

.data
	number1: .asciiz "\nEnter a number: "
	number2: .asciiz "\nEnter another number: "
	result: .asciiz "\nThe total is: "
.text
	main:
		li $v0, 4
		la $a0, number1
		syscall
		
		li $v0, 5
		syscall
		
		move $t0, $v0
		
		li $v0, 4
		la $a0, number2
		syscall
		
		li $v0, 5
		syscall
		
		move $t1,$v0
		
		add $t2, $t0, $t1
		
		li $v0, 4
		la $a0, result
		syscall
		
		li $v0, 1
		move $a0, $t2
		syscall
		
```
###  Create a program that display your name
```
 
 .data
	name: .asciiz "\nRicardo Segovia"
	
.text
	main:
		li $v0, 4
		la $a0, name
		syscall
		
```
## Week 1 Thursday Challenges

### What are real word applications of Javascript
JavaScript is comminly used for creating web pages. It allows us to add dynamic behavior to the webpage and add special effects to the webpage. On websites, it is mainly used for validation purposes. JavaScript helpds us to execute complex actions and also enables the interaction of websites with visitors.
