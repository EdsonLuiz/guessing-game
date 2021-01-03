# Guessing game notes
This notes are about Rust language and not about game logic.

## Import library
```rust
use std::io;
```
This bring io library to scope

## main function
```rust
fn main() {}
```
fn is used to declare a function.  
() indicates that function don't have parameters.  
{} indicates the body of function

## Macros
```rust
println!("Guess the number");
```
println! is a macro to prints a string on screen

## Varaibles
```rust
let mut guess = String::new();
```
```let``` statement is used to create a variable, in Rust variables are immutable.  

```mut```, before the variable name, make variable mutable.  

at the end we have a mutable variable named guess.  

```String::new()``` returns a instance of String growable UTF-8 type.  
```::new()``` is an ***associated function***, that is, is implemented in String type.  

At the end this piece of code has created a mutable variable that is currently bound to a new , empty instance of a String.

## Standard input
```rust
io::stdin().read_line(&mut guess)
    .expect("Failed to read line");
```

```stdin()``` standard input for terminal.

```.read_line(&mut guess)``` input handler function to get input from the user passing one mutable argument to read_line. The &, on mutable argument, indicates that this is a reference.

```read_line``` puts users input into the string we're passing it, also it returns a value, an io::Result.

Result types are ***enumerations*** (enums), enumeration is a type tha can have a fixed set of values, called enum's ***variants***

For Result the variants are ***Ok*** or ***Err***. Ok indicates successfull operation and inside is the successfully generated value. Err means the operation failed, and Err contains information about how or why the operation failed.

An instance of ```io::Result``` has an ```expect``` method that you can call. If this instance of ```io::Result``` is an ***Err*** value, ```expect``` will cause the program to crash and display the message that you passed as an argument to ```expect```. If this instance of ```io::Result``` is an ***Ok*** value, ```expect``` will take the return value that ***Ok*** is holding and return just that value to you so you can use it.