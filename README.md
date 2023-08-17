# brainknot
It's a similar language to Brainfuck. But with some changes

# syntax
it's the same, but alphabet are not counted as comments, you need # before every comment

# what's the difference?
Unlike Brainfuck, brainknot is based on bits instead of bytes.
It uses stack instead of memory line
and it has a variable called current bit

# basic symbols
- \> pops 1 bit from input stack (it's pop-only stack)
- \< pushes current bit to output stack (it's push-only stack)
- \- pops from main stack to current bit (overwrites it)
- \+ pushes current bit to stack (does not change current bit)
- \* flips current bit (like a not gate. Flips 1 to 0 and flips 0 to 1)

# if-else statement
- \[ starts if statement (don't get wrong with loops in Brainfuck)
- \] ends if statement, Example: `[do if,do else]`

if current bit is 1, run first argument (arguments are splited with comma)

if current bit is 0, run second argument

also, you don't need two arguments, you can use `[do smt]` for only if statement, or you can use `[,do smt]` for only else statement.

Example: `>[>*<,><]`

this example takes 2 input and xors them and pushes the result to output

# loop
- \( starts while loop(if current bit is 1)
- \) is end of while loop
- \. breaks the loop.

Example: `*(>[+])*(-<[*]*)`

this examples first moves input to stack until input is 0 (move first line of ones to stack)
then starts another loop which moves stack to output (outputs first line of ones)

# define a function
- \: defines a function.

Name in the right

functionality in left(should be in [] to separate main program with defining, and wont run while defining.)

if you use (parenthesis), function will  be called while defining.

while defining a function you can use stack for input/output of function.
And you call a function with its name, you don't need anything.
But note that you have to separate two rapid functions with space.

you can define recursive functions as well.

Example:
`xor:[-[-*+]]`

This example function is a xor gate

    if first input is 1:
        flip next input and output it
    else:
        output is the same as next input so nothing to do, output is already there

# a final thing i want to mention after all.
i feel dot (.) is useless because loop ends if current bit is 0 or an error happens
so you can define another functionality for it in your interpreter
And i have not mentioned what underline "_" does. So you can define it in your interpreter
also, numbers are used to change which stack are we using.
0 is default, and you can use multiple numbers, like 11 or 69420.

# Version 1

`>` input
`<` output
`[` if
`]` end of if
`*` flip(aka invert/not)

# Version 2

`,` else
`(` loop start
`)` loop check/end
`.` break loop

# Version 3

`-` pop/pull
`+` push
`abc:[]` define
`abc:[]` define and call
`abc` call
` ` seprate funcs

# Version 4

`0` set to stack 0
`1` set to stack 1
`10` set to stack 10
`[a,b,c]` check current bit and then run `c` first, then run `a` or `b` depending on current bit check before

# Version Extra

`^` put a black/white pixel on screen depending on current bit(0 black,1 white) and go to next pixel
`\` next line in screen
`;` update screen/draw frame(and go back to starting pixel)
`{Hello World}` print to console
`/comment/` put a comment
`~` pop without remove
`_` clear stack