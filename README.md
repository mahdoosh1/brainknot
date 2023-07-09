# brainknot
It's a similer language to brainfuck. but with some changes

# syntax
it's the same, but alphabet are not counted as comments, you need # before every comment

# what's the twist?
unlike brainfuck, brainknot is based on bits instead of bytes.
it uses stack instead of memory line
and it has a variable called current bit

# basic symbols
">" pops 1 bit from input stack (it's pop-only stack)
"<" pushes current bit to output stack (it's push-only stack)
"-" pops from main stack to current bit (overwrites it)
"^" pushes current bit to stack (does not change current bit)
"*" flips current bit (like a not gate. flips 1 to 0 and flips 0 to 1)

# if-else statement
"\[" starts if statement (dont get wrong with loops in brainfuck)
"]" stops if statement, Example: `[do if,do else]`
if current bit is 1, run first argument (arguments are splited with camma)
if current bit is 0, run second argument
also you dont need two arguments, you can use `[do smt]` for only if statement
or you can use [,do smt] for only else statement.

Example: `>[>*<,><]`
this example takes 2 input and xors them and pushes the result to output

# loop
"(" starts while loop(if current bit is 1)
")" is end of while loop
"." breaks the loop.

Example: `*(>[^])*(-<[*]*)`
this examples first moves input to stack untill input is 0 (move first line of ones to stack)
then starts another loop which moves stack to output (outputs first line of ones)

# define a function
":" defines a function.
name in the right
functionality in left(should be in [] to seprate main program with defining)
also while defining a function you can use stack for input/output of function.
and you call a function with its name, you dont need anything.
but note that you have to seprate two rapid functions with space

Example:
`xor:[-[-*^]]`
this example function is a xor gate

    if first input is 1:
        flip next input and output it
    else:
        output is the same as next input so nothing to do, output is already there
