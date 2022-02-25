# **LAB REPORT 4**
### 02-25-2022

[HOME](https://jupoon.github.io/cse15l-lab-reports/) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [LAB REPORT 1](https://jupoon.github.io/cse15l-lab-reports/labs/lab1/lab-report-1-week-2) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [LAB REPORT 2](https://jupoon.github.io/cse15l-lab-reports/labs/lab2/lab-report-2) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [LAB REPORT 3](https://jupoon.github.io/cse15l-lab-reports/labs/lab3/lab-report-3)

[My markdown-parse repository](https://github.com/jupoon/markdown-parse)
[Reviewed markdown-parse repository](https://github.com/ericwpei/markdown-parse)

In today's lab we'll be testing three different test files on both my own code, and the code I reviewed. First let's review our test files and establish what they should produce.

#### **Test Snippet 1**
Test Snippet 1 looks like this:

        `[a link`](url.com)

        [another link](`google.com)`

        [`cod[e`](google.com)

        [`code]`](ucsd.edu)


And it should produce a result like this:

`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)


#### **Test Snippet 2**

Test Snippet 2 looks like this:

        [a [nested link](a.com)](b.com)

        [a nested parenthesized url](a.com(()))

        [some escaped \[ brackets \]](example.com)


And it should produce a result like this:

[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)

#### **Test Snippet 3**

Test Snippet 3 looks like this:

        [this title text is really long and takes up more than 
        one line

        and has some line breaks](
            https://www.twitter.com
        )

        [this title text is really long and takes up more than 
        one line](
            https://ucsd-cse15l-w22.github.io/
        )


        [this link doesn't have a closing parenthesis](github.com

        And there's still some more text after that.

        [this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



        )

        And then there's more text


And it should produce a result like this:

[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
    https://ucsd-cse15l-w22.github.io/
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)

And then there's more text