# CPSC 121
## Difference Between Dates Using Command Line Arguments

The objective of this exercise is to write a program which will take two dates from the command line and calculate the difference.

The input shall be two dates in the form of month, day, and year. The month value is valid if it is equal to or greater than 1 and less than or equal to 12. The day value is valid if it is equal to or greater than 1 and less than or equal to 31. The day value is valid if it is greater than 1 and less than 4 billion.

The algorithm that you shall use is 
1. Parse the two dates from the command line arguments
1. Convert the date to the number of days since day 0
1. Subtract the first date from the second date
1. Report the resulting calculations as the number of days


You must use the formula provided in this README to convert a date to the number of days since day 0.

The formula to convert a given date to the number of days since day 0 is
![\Huge{365 \times y + \frac{y}{4} - \frac{y}{100} + \frac{y}{400} + d + \frac{153 \times m + 8}{5}}](https://render.githubusercontent.com/render/math?math=%5CHuge%7B365%20%5Ctimes%20y%20%2B%20%5Cfrac%7By%7D%7B4%7D%20-%20%5Cfrac%7By%7D%7B100%7D%20%2B%20%5Cfrac%7By%7D%7B400%7D%20%2B%20d%20%2B%20%5Cfrac%7B153%20%5Ctimes%20m%20%2B%208%7D%7B5%7D%7D). In this formula, _y_ is the year, _m_ is the month, and _d_ is the day. Furthermore, if the month is Januar (1) or February (2), then add 12 to _m_ and subtract 1 from _y_. The result of the formula is the number of days so there are no fractional results. (In other words, no decimal points.)

The formula must be implemented as a function with the following prototype:
```
int date_to_days(int month, int days, int year);
```
Failing to write this function and use it in the main function will forfeit 3 points.

To convert a string to an integer, please use [`stoi( )`](https://en.cppreference.com/w/cpp/string/basic_string/stol) or [`stol( )`](https://en.cppreference.com/w/cpp/string/basic_string/stol).

Your program shall be in one file named datedifference.cpp. The name of the program shall be `datedifference`. The included `Makefile` includes the targets:
* all: builds the project
* clean: removes object and dependency files
* spotless: removes everything the clean target removes and all binaries
* format: outputs a [`diff`](https://en.wikipedia.org/wiki/Diff) showing where your formatting differes from the [Google C++ style guide](https://google.github.io/styleguide/cppguide.html)
* tidy: output of the linter to give you tips on how to improve your code

To build your program, use the command `make` or `make all`. 

## Example Output
To earn full credit, your submission must match the format of the example output. In other words, aside from the portions of user input, your program ought to prompt and output exactly as the example given.

```
$ make all
$ ./datedifference
You need to provide two dates.
For example datedifferance 1 1 2019 1 1 2020
$ ./datedifference  1 1 2019 1 1 2020
The number of days between 1-1-2020 and 1-1-2019 is 365
$ ./datedifference  1 1 2016 1 1 2017
The number of days between 1-1-2017 and 1-1-2016 is 366
$ ./datedifference  8 1 2020 9 8 2020
The number of days between 9-8-2020 and 8-1-2020 is 38
$ ./datedifference  9 8 2020 8 1 2020
The number of days between 8-1-2020 and 9-8-2020 is -38
```

## Submission
Use git to commit and push your changes back to your repository on GitHub. Remember that you are evaluated on the quality of your git log messages; please do not ignore them.
