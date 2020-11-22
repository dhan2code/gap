## GAP - Groups, Algorithms, Programming - a System for Computational Discrete Algebra

1. [Installation](#installation)

### Installation
Choose your preferred archive format and [download](https://www.gap-system.org/Download/) the corresponding archive. Extract the file the details will be present in the *Install.md*. Now for **vim** and **emacs** we can do something special, check the *etc* folder on the downloaded file. By placing the *gaps.vim* in the *~/.vim/syntax* and *gap_indent.vim* in the *~/.vim/indent* we get syntax and indentation respectively for gap files. 

If you can't find the *etc* file check my dotfiles [here.](https://github.com/dhan2code/dotfiles/tree/master/vim)

And for auto detection of the gap file, create a *gaps.vim* file in *~/.vim/ftdetect* and add the following lines.
```
autocmd BufRead,BufNewFile *.g,*.gi,*.gd set filetype=gap comments=s:##    \ \ ,m:##\ \ ,e:##\ \ b:#
```

### Running GAP.
Opening GAP in terminal by running `gap program.g`. We can load a gap to an existing `gap` session by using the `Read("path");`. Please note the use of `;` after every command as an end to an command. Now we can figure out `for` and `while` loops by example.

```
i := 0;
for i in [1..10] do
	i := i + 1;
od;
```
```
i :=0;
while i < 10 do
	i := i + 1;
od;
```
Here's an example of if conditional.
```
n := 5;
if n=1 then
	return 0;
elif n<1 then
	return -1;
else
	return 1;
fi;

```
And we have two ways to define a function.
```gap
# first way.
cubed:= x -> x^3;

# second way.
fib := function(n)
    if n=1 then
        return 1;
    elif n<1 then
        return 0;
    else
        return fib(n-1)+fib(n-2);
    fi;
end;
```

### Variables vs Objects.
  Specified by a sequence of letters and digits (including at least one letter), and their meaning depends on what has been assigned to them. An assignment is done by a GAP command `sequence_of_letters_and_digits := meaning,` where the sequence on the LHS is called the *identifier* of the variable and it serves as it's name. Then meaning on the RHS is made up of **GAP Objects**. 

 We will use the term **object** to denote something that can be assigned to a variable.

 **Example of Objects:**

- Numbers.
- Strings (Characters).
- Matrices.
- List (A collection of objects that have **holes** and multiplicity)
- Set (No holes and no multiplicity)
- Range (its a list with increment 1)



> I have made a cheatsheet for `gap`, check it out [here.](Cheatsheet.md)

