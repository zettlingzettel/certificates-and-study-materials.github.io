# Certificate 1
## Week 1

2023 June 13th (challenge-day-1)
### Hands-On Programming with R - Chapter 2
#### 2.1-2.2
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~
Functions:
* ls()
* The colon operator (:) returns every integer between two integers. It is an easy way to create a sequence of numbers.
* a <- 1
[1] 1
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~

You can name an object in R almost anything you want, but there are a few rules. First, a name cannot start with a number. Second, a name cannot use some special symbols, like ^, !, $, @, +, -, /, or *:

R is case sensitive

 R does not always follow the rules of matrix multiplication. Instead, R uses element-wise execution.

 R will apply the same operation to each element in the set. So for example, when you run die - 1, R subtracts one from each element of die.

If you give R two vectors of unequal lengths, R will repeat the shorter vector until it is as long as the longer vector, and then do the math

Element-wise operations will ensure that values from one observation or case are only paired with values from the same observation or case.
[ This is where the elements in the same row are multiplied by one another. ]

vector recycling
If the length of the short vector does not divide evenly into the length of the long vector, R will return a warning message.

But don’t think that R has given up on traditional matrix multiplication. You just have to ask for it when you want it. You can do inner multiplication with the %*% operator and outer multiplication with the %o% operator.

#### 2.3
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~
Functions:
sample takes two arguments: a vector named x and a number named size. sample will return size elements from the vector.
```R
sample(x = 1:4, size = 2)
## 3 2
```

If you’re not sure which names to use with a function, you can look up the function’s arguments with args. To do this, place the name of the function in the parentheses behind args.
```R
args(round)
## function (x, digits = 0) 
## NULL
```
```R
sample(die, size = 2, replace = TRUE)
## 5 5
## the argument replace = TRUE causes sample to sample with replacement. . Each value has a chance of being selected each time. A sample of size one that is independent of the other values.
```

```R
dice <- sample(die, size = 2, replace = TRUE)
dice
## 2 4

sum(dice)
## 6
```
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~
 
The data that you pass into the function is called the function’s argument. 

When you link functions together, R will resolve them from the innermost operation to the outermost. 

You can give a function as many arguments as you like as long as you separate each argument with a comma.

You can pass a new value to an optional argument if you want, and R will use the default value if you do not. 

#### 2.4.1
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~
Functions:
```R 
my_function <- function() {
  die <- 1:6
  dice <- sample(die, size = 2, replace = TRUE)
  sum(dice)
}
```

R ignores spaces and line breaks and executes one complete expression at a time.

Giving the bones argument a default value. To do this, set bones equal to a value when you define roll2:

```R
roll2 <- function(bones = 1:6) {
  dice <- sample(bones, size = 2, replace = TRUE)
  sum(dice)
}
```
Now you can supply a new value for bones if you like, and roll2 will use the default if you do not.
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~

#### 2.6 Scripts
R will run whichever line of code your cursor is on. If you have a whole section highlighted, R will run the highlighted code. Alternatively, you can run the entire script by clicking the Source button. Don’t like clicking buttons? You can use Control + Return as a shortcut for the Run button. On Macs, that would be Command + Return.

Scripts are multi-line code (console has single-line command line).

CREATING A FUNCTION FROM THE SCRIPT
RStudio comes with a tool that can help you build functions. To use it, highlight the lines of code in your R script that you want to turn into a function. Then click Code > Extract Function in the menu bar. RStudio will ask you for a function name to use and then wrap your code in a function call. It will scan the code for undefined variables and use these as arguments.


2023 June 14th (challenge-day-2)
### R for Data Science - Chapter 4
#### 4.1
Alt + - (the minus sign).
Object names must start with a letter, and can only contain letters, numbers, _ and .


```R
seq(1, 10)
```
surrounding the assignment with parentheses, which causes assignment and “print to screen” to happen.

Alt + Shift + K

2023 June 15th-16th (challenge-day-3-4)
### Fundamentals of R Summary
Objects can be created with the assign operator, <-, and named using letters, digits, dots, and underscores. Note that a name must start with a letter and is case sensitive. 

Objects have two intrinsic properties: mode and length. The mode represents the element type: numeric, character, complex, and logical. The length is the number of elements in the object.

Vector, Matrix, Array, List, Dataframe

```R
x <- 10             # numeric vector 
mode(x)

y <- "my vector"    ### character vector
mode(y)

z <- 10i            ### complex vector
mode(z)

j <- TRUE           ### logical vector
mode(j)
```

```R
dim(data) 
### The dim function of the R programming language returns the dimension (e.g. the number of columns and rows) of a matrix, array or data frame.
```

```R
The mode is the value that has highest number of occurrences in a set of data. Unike mean and median, mode can have both numeric and character data. R does not have a standard in-built function to calculate mode.


If the mode() function in R gives a result of numeric, it means that the vector or matrix has no mode. This can happen if the vector or matrix has all unique values, or if the values in the vector or matrix are evenly distributed.
```

```R
%%
Modulus
% / %
Integer Division
```

```R
Functions:
Description
?() or help()
Access the documentation and help file for a particular function
install.packages()
Download and install an R package
library()
Loads an R package into the working environment
setwd()
Set the working directory
getwd()
Get the working directory
c()
Create a vector
as.numeric()
Converts an object to a numeric vector
as.logical()
Converts an object to a logical vector
as.character()
Converts and object to a character vector
sum()
Returns the sum of all input values
length()
Returns the lenght of the obejct
mean()
Returns the arithmetic mean of the vector
median()
Returns the median of the vector
sample()
Returns a specificed size of elements from the object
replicate()
Repeats an expression a specific number of times
hist()
Creates a histogram of given data values
```

2023 June 14th (challenge-day-5)

Document Everything

Start with the question and the raw data
All files are text files

Platform independence
Future-proof
Make code reachable

Comments
Formatting (indentation)
Meaningful names
Each script does one task
