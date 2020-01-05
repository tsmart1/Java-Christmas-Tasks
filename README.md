## Java-Christmas-Tasks

# Task

In this repository, you will find a solution to the Fizz Buzz program you attempted before joining Sparta Global. 
* You need to investigate how you can *test* if this program works according the specification. 
* Next, if you find any problems, repair them and retest the program
* Create a short markdown file that explains your testing process, the changes you made if any, and the results of your tests before and after the changes were made

# Testing Process

In testing the Fizz Buzz program, I decided to take the two test cases already included in the code and run (and adjust) the code until the desired result is delivered. In order to do this, I had to work out what the ‘correct’ results would be. To do this, I used [this](https://www.dcode.fr/multiples-list-number) website in order to quickly find a list of multiples of 3, 5 and 3 & 5.

# Test Case 1

The first test case calls for the Fizz Buzz program to be ran for numbers between 1 and 100. Therefore, the multiples should be as follows:
*	Multiples of 3 (“Fizz”): 3, 6, 9, 12, 18, 21, 24, 27, 33, 36, 39, 42, 48, 51, 54, 57, 63, 66, 69, 72, 78, 81, 84, 87, 93, 96, 99
*	Multiples of 5 (“Buzz”): 5, 10, 20, 25, 35, 40, 50, 55, 65, 70, 80, 85, 95, 100
*	Multiples of 3 and 5 (“FizzBuzz”): 15, 30, 45, 60, 75, 90

Now that I know what my expected output should be, I will run the program and check the output to see whether it is correct along the above lines – with the “Fizz”, “Buzz” and “FizzBuzz” in the correct positions.

Relevant code line

> System.out.println(fizzBuzzGenerator.FizzBuzz(1,100).toString());

Output:

> [1, FizzBuzz, 3, 4, FizzBuzz, 6, FizzBuzz, FizzBuzz, 9, 10, FizzBuzz, FizzBuzz, 13, FizzBuzz, 15, 16, FizzBuzz, 18, 19, FizzBuzz, 21, FizzBuzz, FizzBuzz, 24, 25, FizzBuzz, FizzBuzz, 28, FizzBuzz, 30, 31, FizzBuzz, 33, 34, FizzBuzz, 36, FizzBuzz, FizzBuzz, 39, 40, FizzBuzz, FizzBuzz, 43, FizzBuzz, 45, 46, FizzBuzz, 48, 49, FizzBuzz, 51, FizzBuzz, FizzBuzz, 54, 55, FizzBuzz, FizzBuzz, 58, FizzBuzz, 60, 61, FizzBuzz, 63, 64, FizzBuzz, 66, FizzBuzz, FizzBuzz, 69, 70, FizzBuzz, FizzBuzz, 73, FizzBuzz, 75, 76, FizzBuzz, 78, 79, FizzBuzz, 81, FizzBuzz, FizzBuzz, 84, 85, FizzBuzz, FizzBuzz, 88, FizzBuzz, 90, 91, FizzBuzz, 93, 94, FizzBuzz, 96, FizzBuzz, FizzBuzz, 99]

Issues:
*	All words are showing as “FizzBuzz” rather than “Fizz” or “Buzz” respectively
*	Words are placed in the wrong location (e.g. replacing 2 which is on neither of my lists and not replacing 15 which is on all)
*	Numbers only go up to 99, rather than 100

Fixes:

The next stage was to look at the code (specifically FizzBuzzGenerator.java) in order to look for corrections for these issues. Changes made were as follows:
*	On line 14, changed “||” (an or) to “&&” (an and) in order to ensure that “FizzBuzz” only triggers when a number is a multiple of 3 and 5
*	On line 7, changed it to return ‘numerator % Denominator == 0’ as a modulo of 0 signifies a number is a multiple so therefore would return true if it is and false if it is not
*	On line 13, changed the for loop condition to be “i <= endNumber” so that it includes the upper limit called for
Upon making these changes I re-ran the same test case and got this output:

> [1, 2, Fizz, 4, Buz, Fizz, 7, 8, Fizz, Buz, 11, Fizz, 13, 14, FizzBuzz, 16, 17, Fizz, 19, Buz, Fizz, 22, 23, Fizz, Buz, 26, Fizz, 28, 29, FizzBuzz, 31, 32, Fizz, 34, Buz, Fizz, 37, 38, Fizz, Buz, 41, Fizz, 43, 44, FizzBuzz, 46, 47, Fizz, 49, Buz, Fizz, 52, 53, Fizz, Buz, 56, Fizz, 58, 59, FizzBuzz, 61, 62, Fizz, 64, Buz, Fizz, 67, 68, Fizz, Buz, 71, Fizz, 73, 74, FizzBuzz, 76, 77, Fizz, 79, Buz, Fizz, 82, 83, Fizz, Buz, 86, Fizz, 88, 89, FizzBuzz, 91, 92, Fizz, 94, Buz, Fizz, 97, 98, Fizz, Buz]

Looking at the three changes I made, they seem to have had the desired effect and fixed the three issues I found – however has created an additional issue, “Buzz” is spelt as “Buz”. I corrected this by adjusting the spelling on line 16 and that corrects the output to as follows:

> [1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz, 16, 17, Fizz, 19, Buzz, Fizz, 22, 23, Fizz, Buzz, 26, Fizz, 28, 29, FizzBuzz, 31, 32, Fizz, 34, Buzz, Fizz, 37, 38, Fizz, Buzz, 41, Fizz, 43, 44, FizzBuzz, 46, 47, Fizz, 49, Buzz, Fizz, 52, 53, Fizz, Buzz, 56, Fizz, 58, 59, FizzBuzz, 61, 62, Fizz, 64, Buzz, Fizz, 67, 68, Fizz, Buzz, 71, Fizz, 73, 74, FizzBuzz, 76, 77, Fizz, 79, Buzz, Fizz, 82, 83, Fizz, Buzz, 86, Fizz, 88, 89, FizzBuzz, 91, 92, Fizz, 94, Buzz, Fizz, 97, 98, Fizz, Buzz]

# Test Case 2

The second test case calls for the Fizz Buzz program to be ran for numbers between 20 and 50. Therefore, the multiples should be as follows:
*	Multiples of 3 (“Fizz”): 21, 24, 27, 33, 36, 39, 42, 48
*	Multiples of 5 (“Buzz”): 20, 25, 35, 40, 50
*	Multiples of 3 and 5 (“FizzBuzz”): 30, 45

I ran my updated code and received the following output:

Relevant code line

> System.out.println(fizzBuzzGenerator.FizzBuzz(20,50).toString());

Output:

> [Buzz, Fizz, 22, 23, Fizz, Buzz, 26, Fizz, 28, 29, FizzBuzz, 31, 32, Fizz, 34, Buzz, Fizz, 37, 38, Fizz, Buzz, 41, Fizz, 43, 44, FizzBuzz, 46, 47, Fizz, 49, Buzz]

This output is as expected and therefore I am satisfied the test cases pass and that the code works as required to by the specification.

# The final issue – Form of output

My final issue with the code was how it should be outputted. The specification states the following:
* *fizzBuzzGenerator(1,15) should return ["1", "2", "Fizz", "4", "Buzz", "Fizz", "7", "8", "Fizz", "buzz", "11", "Fizz", "13", "14", "FizzBuzz"]*
* *Keep note that the list must contain String items*

Currently my code would not place the numbers or words in quotation marks, though I am unsure whether this is required or if it is just there to emphasise that they should be string items (which they are). However, as the specification gives a clear example of the expected output, I added quotation marks (via escape characters) to the words and to numbers added (via concatenation). This now means the results are as follows:

Test Case 1

> ["1", "2", "Fizz", "4", "Buzz", "Fizz", "7", "8", "Fizz", "Buzz", "11", "Fizz", "13", "14", "FizzBuzz", "16", "17", "Fizz", "19", "Buzz", "Fizz", "22", "23", "Fizz", "Buzz", "26", "Fizz", "28", "29", "FizzBuzz", "31", "32", "Fizz", "34", "Buzz", "Fizz", "37", "38", "Fizz", "Buzz", "41", "Fizz", "43", "44", "FizzBuzz", "46", "47", "Fizz", "49", "Buzz", "Fizz", "52", "53", "Fizz", "Buzz", "56", "Fizz", "58", "59", "FizzBuzz", "61", "62", "Fizz", "64", "Buzz", "Fizz", "67", "68", "Fizz", "Buzz", "71", "Fizz", "73", "74", "FizzBuzz", "76", "77", "Fizz", "79", "Buzz", "Fizz", "82", "83", "Fizz", "Buzz", "86", "Fizz", "88", "89", "FizzBuzz", "91", "92", "Fizz", "94", "Buzz", "Fizz", "97", "98", "Fizz", "Buzz"]

Test Case 2

> ["Buzz", "Fizz", "22", "23", "Fizz", "Buzz", "26", "Fizz", "28", "29", "FizzBuzz", "31", "32", "Fizz", "34", "Buzz", "Fizz", "37", "38", "Fizz", "Buzz", "41", "Fizz", "43", "44", "FizzBuzz", "46", "47", "Fizz", "49", "Buzz"]
