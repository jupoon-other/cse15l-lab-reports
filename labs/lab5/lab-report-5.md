# **LAB REPORT 5**
### 03-11-2022

[HOME](https://jupoon.github.io/cse15l-lab-reports/) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [LAB REPORT 1](https://jupoon.github.io/cse15l-lab-reports/labs/lab1/lab-report-1-week-2) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [LAB REPORT 2](https://jupoon.github.io/cse15l-lab-reports/labs/lab2/lab-report-2) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [LAB REPORT 3](https://jupoon.github.io/cse15l-lab-reports/labs/lab3/lab-report-3) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [LAB REPORT 4](https://jupoon.github.io/cse15l-lab-reports/labs/lab4/lab-report-4) 


#### **Intro**

Today we will be reviewing my lab group's code when ran with the commonmark-spec tests. To run the tests, we used something called bash scripting to run all 652. The command looks like this:

`bash script.sh > results.txt`

and we can then use vim to look at results.txt where the output is stored.

![Image](ss_bashscript.png)

But out of all 652 test results, how do I check which results I have that differ from the professors? I ran this line of code in order to see.

`diff lab9/results.txt lab9_mine/results.txt`

Out of all the tests where there were code differences, I chose test 32.md and 495.md

#### **Test 32.md**
This test file contains the following content:

`[foo](/f&ouml;&ouml; "f&ouml;&ouml;")`

Our lab's output: 

`[]`

Their output:

`[/f&ouml;&ouml; "f&ouml;&ouml;"]`

Our lab group's output should be correct, since the content within the brackets is not a valid link, containing a "space" character. When spaces appear in links, its should be formatted with %20 rather than a blank space, otherwise the link is not valid

* Example: a link like `www.my link.com` should be written as `www.my%20link.com` 

This occurs because their implementation does not catch blank spaces that exist in potential links, which can be easily remedied through the use of `indexOf(" ")` to check whether or not the link substring within openParen and closeParen contains a blank space. We can also use `indexOf("%20")` to check for links that correctly have spaces written into them.


#### **Test 495.md**

This test file contains the following content:

`[link](foo(and(bar)))`

Our lab's output:

`[foo(and(bar))]`

Their output:

`[foo(and(bar]`


Our lab group's output should be correct, since it includes everything within the first and last parenthesis. Their implementation stops the collection of the substring at the first closeParen, which is not correct. To fix this, you can use the `indexOf()` method again to check for the last closing parenthesis before the next open bracket, and store everything between the first openParen and last closeParen to be printed in the output.


### **With that, my CSE 15L career is over :3 Goodbye!**

![gif](https://www.google.com/url?sa=i&url=https%3A%2F%2Fgiphy.com%2Fexplore%2Fcat-goodbye&psig=AOvVaw3RRYaafMd9qpKwMnvgkfHe&ust=1647400411026000&source=images&cd=vfe&ved=0CAsQjRxqFwoTCOC09feSx_YCFQAAAAAdAAAAABAa)


