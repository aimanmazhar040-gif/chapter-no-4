# chapter-no-4
Exercises
4.11 Identify and correct the error(s) in each of the following:
a) if (age >= 65);
cout << "Age is greater than or equal to 65" << endl;
else
cout << "Age is less than 65 << end1";
Error:
 The semicolon ; ends the if statement, so else becomes invalid.
And the quote " is missing before << endl.
Correction:
if (age >= 65)
    cout << "Age is greater than or equal to 65" << endl;
else
    cout << "Age is less than 65" << endl;

b) if (age >=65)
cout << "Age is greater than or equal to 65" << endl; 
else;
cout << "Age is less than 65 << endl";
Error:
Semicolon after else makes it useless.
Also << endl" is written incorrectly.
Correction:
if (age >= 65)
    cout << "Age is greater than or equal to 65" << endl;
else
    cout << "Age is less than 65" << endl;

c) int x =1, total;
while (x<=10)
{ total += x;
 ++x ;
}
Error:
Total is not initialized, so it contains garbage value.
Correction:
int x = 1, total = 0;
while (x <= 10)
{
    total += x;
    ++x;
}
d) while (x<=100)
total += x;
x++;
Error:
Missing { }, so only total += x; is inside loop
 x++ runs outside, causing an infinite loop.
Correction:
while (x <= 100)
{
    total += x;
    x++;
}
e) while (y>0)
{
cout << y << endl;
 ++y;}
Error:
y is increasing, but condition is y > 0
 Causes infinite loop
Correction:
while (y > 0)
{
    cout << y << endl;
    --y;
}



4.12 What does the following program print?
#include <iostream>
using namespace std;

int main()
{
    int y;
    int x = 1;
    int total = 0;
    while (x <= 10)
    {
        y = x * x;
        cout << y << endl;
        total += y;
        x++;
    }

    cout << "Total is " << total << endl;
    return 0;
}
Output:
1
4
9
16
25
36
49
64
81
100
Total is 385
4.21 What does the following program print?


#include <iostream>
using namespace std;
int main()
{
int count =1; // initialize count
while (count<= 10)//loop 10 times
{//output line of text
cout << (count %2?”****”:”++++++++<< endl; 
++count; // increment count
}// end while
}// end main
Step-by-Step Output
count	count % 2	Printed
1	1 (odd)	****
2	0 (even)	++++++++
3	1	****
4	0	++++++++
5	1	****
6	0	++++++++
7	1	****
8	0	++++++++
9	1	****
10	0	++++++++
Final output :
****
++++++++
****
++++++++
****
++++++++
****
++++++++
****
++++++++

4.22 What does the following program print?
#include <iostream>
using namespace std;
int main()
{
    int row = 10;      // initialize row
    int column;       // declare column
    while (row >= 1)  // loop until row < 1
    {
    column = 1;   // set column to 1
    while (column <= 10) // loop 10 times
        {
     cout << (row % 2 ? "<" : ">");
    ++column;
        }
     --row;        // decrement row
      cout << endl; // new line
    }
    return 0;
}
Row-wise Output Explanation
Row	Even / Odd	Printed Symbol
10	Even	>
9	Odd	<
8	Even	>
7	Odd	<
6	Even	>
5	Odd	<
4	Even	>
3	Odd	<
2	Even	>
1	Odd	<
Final Output
>>>>>>>>>> 
<<<<<<<<<<
>>>>>>>>>> 
<<<<<<<<<<
>>>>>>>>>> 
<<<<<<<<<<
>>>>>>>>>> 
<<<<<<<<<<
>>>>>>>>>> 
<<<<<<<<<<
Question 4.23 (Dangling-else Problem)
Given:
x = 9
y = 11
Rule: else always matches the nearest unmatched if
4.23 (a)
if (x < 10)
    if (y > 10)
        cout << "*****" << endl;
    else
        cout << "#####" << endl;
cout << "$$$$$" << endl;
Step-by-step
x < 10 → 9 < 10 ✅ true
y > 10 → 11 > 10 ✅ true
So "*****" is printed
else is ignored
cout << "$$$$$" runs always
Output:
*****
$$$$$
4.23 (b)
if (x < 10)
    if (y > 10)
        cout << "*****" << endl;
    else
        cout << "#####" << endl;
        cout << "$$$$$" << endl;
Important
The else belongs to if (y > 10)
cout << "$$$$$" is outside both ifs
Step-by-step
x < 10 → true
y > 10 → true → "*****" prints
cout << "$$$$$" prints anyway
Output
*****
$$$$$
