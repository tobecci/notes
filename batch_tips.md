# Cheat Sheet for Batch programming

## creating and accessing variables

set name=yourname
or
set name="yourname"

we access the name variable using %name%

## hide commands on the command line

we do this by using 
```
@echo off
```

## if statements
```
IF (condition) (command to run)
e.g IF %a%==%b% (echo they are equal)
```

## if else statements

```
IF (condition) (command to run) ELSE (command to run)  
e.g IF %a%==%b% (echo they are equal) ELSE (echo they are not equal) 
```

>you can chain two commands in () by using && e.g (echo hello && echo world)

