# lintr-cli
Bash wrapper for lintr: lint your R code outside of R, not inside

## Requirements

- A shell (duh!)
- R (obviously)
- [lintr](https://github.com/jimhester/lintr)

## Installation

1. Enter R and type

  ```R
  install.packages("lintr")
  ```

2. Copy `lintr-cli` to a folder in your path, or in a folder nearby

## How to use it

```sh
./lintr-cli bad.R
```

```R
> lintr::lint("bad.R")
bad.R:1:5: style: Use <-, not =, for assignment.
fun = function(one)
    ^
bad.R:2:1: style: Opening curly braces should never go on their own line and should always be followed by a new line.
{
^
bad.R:3:5: style: Words within variable and function names should be separated by '_' rather than '.'.
    one.plus.one <- oen +1 
    ^~~~~~~~~~~~
bad.R:3:5: warning: local variable ‘one.plus.one’ assigned but may not be used
    one.plus.one <- oen +1 
    ^~~~~~~~~~~~
bad.R:3:21: warning: no visible binding for global variable ‘oen’, Did you mean 'one'?
    one.plus.one <- oen +1 
                    ^~~
bad.R:3:25: style: Put spaces around all infix operators.
    one.plus.one <- oen +1 
                        ^~
bad.R:3:27: style: Trailing whitespace is superfluous.
    one.plus.one <- oen +1 
                          ^
bad.R:4:13: style: Variable and function names should be all lowercase.
    four <- newVar <- matrix(1:10, nrow = 2)
            ^~~~~~
bad.R:4:13: warning: local variable ‘newVar’ assigned but may not be used
    four <- newVar <- matrix(1:10, nrow = 2)
            ^~~~~~
bad.R:5:9: style: Do not place spaces around code in parentheses or square brackets.
    four[ 1, ]
        ^
bad.R:6:12: style: Only use double-quotes.
    txt <- 'hi'
           ^~~~
bad.R:7:5: warning: local variable ‘three’ assigned but may not be used
    three <- two+ 1
    ^~~~~
bad.R:7:14: warning: no visible binding for global variable ‘two’, Did you mean 'txt'?
    three <- two+ 1
             ^~~
bad.R:7:17: style: Put spaces around all infix operators.
    three <- two+ 1
               ~^
bad.R:8:7: style: Place a space before left parenthesis, except in a function call.
    if(txt == 'hi') 4
      ^
bad.R:8:15: style: Only use double-quotes.
    if(txt == 'hi') 4
              ^~~~
bad.R:9:6: style: Closing curly-braces should always be on their own line, unless it's followed by an else.
    5}
     ^
bad.R:10:1: error: unexpected '}'
}
^
```
