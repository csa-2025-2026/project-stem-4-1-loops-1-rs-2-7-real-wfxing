# unit-4-1-assignment

## Git Config
```
git config user.name "user"
git config user.email "email"
```

## Compiling and Running Java Programs
Note that since the shape classes are separate classes, you will need to compile ALL the files (at least one time).  You can do this by running
```
javac *.java
```
The star means to compile every file that is a Java file type.

Run your code by running
```
java Main.java
```

After you compile the shape classes, you only need to compile and run `Main.java` as usual.

# Instructions  

## Problem 1
Write a program that requests that the user inputs any non-negative numbers, and if the user inputs the number -1, the program should print the sum of all numbers. Make sure -1 does not get added to the total sum.

Sample run:
```
Enter any numbers (Enter -1 to stop)
2
12
3
5
-1
Sum is 22
```

## Problem 2
Write a program that asks the user how many numbers they wish to input.  The computer will then prompt for that many inputs,
and find the maximum value from the numbers inputted.

Hint: You need to initialize your maximum value to some value for your program to work.  You can either use an if-statement
inside of your loop to check whether the user has entered a value; if it is the first value entered, you can set your max to this
value; otherwise, you can check if the user has entered something larger than your max, and set it to the user-input instead.

Alternatively, you can merely set your maximum value to `Integer.MIN_VALUE`.

Sample Run:
```
Enter the Scores:
44
22
88
-1

The largest score is 88
```

## Problem 3
Write a program that requests the user to input a word, then prints out the first two letters - then skips a letter - then prints out the next two consecutive letters - then skips a letter - then this process repeats through the rest of the word.

Hint #1 - You will need to use the substring method inside a loop in order to determine which letters of the String should be printed.

Hint #2 - You can use the length method on the String to work out when this loop should end.

Sample run #1:
```
Input a word:
calculator
cacuatr
```
Sample run #2:
```
Input a word:
okay
oky
```

## Sample Solutions
```java
// Problem 1
Scanner sc = new Scanner(System.in);
int x = 0;
int sum = 0;

System.out.println("Enter any numbers greater than 0.  Enter -1 to stop");
while (x != -1)
{
  x = sc.nextInt();
  sum += x;
}

sum++; // To account for -1

System.out.println("Sum is " + sum);

// Problem 2
Scanner sc = new Scanner(System.in);
int input;
int max = Integer.MIN_VALUE; // Guarantees I always get the maximum value
int count = 0;
System.out.println("How many numbers do you wish to input?");
count = sc.nextInt();

System.out.println("Enter the scores:");
int i = 0;
while (i < count)
{
  input = sc.nextInt();
  if (input > max)
  {
    max = input;
  }
  i++;
}

System.out.println("The largest score is " + max);

// Problem 3
Scanner sc = new Scanner(System.in);
String str;

System.out.println("Input a word:");
str = sc.nextLine();

int index = 0;
while (index < str.length())
{
  // The index of every third letter is equal to 2 modulo 3
  if (index % 3 != 2)
  {
    System.out.print(str.substring(index, index+1));
  }
}
```
