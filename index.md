## GAP - Groups, Algorithms, Programming - a System for Computational Discrete Algebra

### Installation
Choose your preferred archive format and [download](https://www.gap-system.org/Download/) the corresponding archive. Extract the file the details will be present in the *Install.md*. Now for **vim** and **emacs** we can do something special, check the *etc* folder on the downloaded file. By placing the *gaps.vim* in the *~/.vim/syntax* and *gap_indent.vim* in the *~/.vim/indent* we get syntax and indentation respectively for gap files. 

If you can't find the *etc* file check my dotfiles [here.](https://github.com/dhan2code/dotfiles/tree/master/vim)

And for autodetection of the gap file, create a *gaps.vim* file in *~/.vim/ftdetect*} and add the following lines.
```
autocmd BufRead,BufNewFile *.g,*.gi,*.gd set filetype=gap comments=s:##    \ \ ,m:##\ \ ,e:##\ \ b:#
```
### Running GAP.
Opening GAP in terminal by runing `gap`.
To load a GAP file (saved in `.g` format) by Using the` Read("path"); `

### Syntax and thoughts on GAP.
After every command use `;`, the semicolon can be thought of as an end of an command.

### Loops for and while, and IF
Let's figure this out by examples

#### For loop.
```
i := 0;
for i in [1..10] do
	i := i + 1;
od;
```
#### While loop.
```
i :=0;
while i < 10 do
	i := i + 1;
od;
```
#### IF function.
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
#### Defining Functions (Fibonacci function.)
```
cubed:= x -> x^3;
cubed(5);
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

## Variables vs Objects.
 **Variables:** Specified by a sequence of letters and digits (including at least one letter), and their meaning depends on what has been assigned to them. An assignment is done by a GAP command `sequence_of_letters_and_digits := meaning,` where the sequence on the LHS is called the *identifier* of the variable and it serves as it's name. Then meaning on the RHS is made up of **GAP Objects**. 

 We will use the term **object** to denote something that can be assigned to a variable.

 **Example of Objects:**

- Numbers
- Strings (Characters)
- Matrices
- List (A collection of objects that have **holes** and multiplicity)
- Set (No holes and no multiplicity)
- Range (its a list with increment 1)

## Cheatsheet

| Name | Input | Output | Remarks|
|:-|:-|:-|:-|
|`Read("filepath")`| Gaps script | - | Add the gaps file to current session.|
|`Append(lista,listb)`| Lists | List | Concatenate two lists.|
|`Add(list,element)`| List, object| List | Add an element to list.|
|`Length(list)`| List | Number | The length of an list|
|`Position(list,object)`| List | Object | Position of an object in a list|
|`ShallowCopy(list)`| List | List | Copy of a list to a new identifier.|
|`AddSet(set,element)`| Set, element | Set | Adding an element to a set. |
|`Product(list)`| List | Number | Multiplying each element of a list |
|`List(list,function)`| List, function | List | The function acts on the list.|
|`Filtered(list,statement)`| List, statement | List | The list is filtered.|
|`ForAll(list,statement)`| List, statement | Bool | True for all elements.|
|`Display(object)`| Object |-| Displays object |

