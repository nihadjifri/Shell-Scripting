Hi, the first fact that i want to make u clear is,

what is a command and what is an executable file.

what ever we type on a prompt expecting an output, we can generally call it as the command that 
we want to execute on that machine. it can be our normal commands like [ eg1: ls,pwd,mkdir,echo etc] 
as well as the compiled executables of your normal c programes that we generally call with names.
./filename [ eg2 : ./a.out, ./test]

here the basic rule to execute anything command through the prompt is by providing the full path to 
the executable file of that command, here the path can be an absolute path or a relative path.
eg::
 absolute path : /bin/ls
 Relative path : ./a.out

but most of the times when we execute any command we generally won't provide any path right, why?

here if i want to execute some executable from some specific directory in our system, either we should
change our directory to that path and execute our file with ./filename or we can provide a relative path
to that directory [eg : suppose if we want to execute a.out present on my parent directory ./../a.out]

but what if we want to execute some of our executable file from anywhere in the system?
we save those files in our default library path right?
so if we want to execute any command whose executable is saved in any of the path locations then we 
can just call by their names eg: ls,pwd instead of /bin/ls, /bin/pwd.

summary: 
========
if we run any command on our system with out path, shell will check for an executable with a matching 
name on our default path locations and if it find a match it will execute the same and if not
it will tell u "command not found". otherwise we should either provide an absolute or relative path 
to the executable that we want to execute.

Example:
=======
Now lets try to execute a c programe inside a shell script and lets try to redirect the output to 
another temperrory file.
so here in this repository/project i have a simple c program (program.c) that prints something to the 
standard output. i have compiled the same to another name "test"
$vi program.c

#include<stdio.h>
int main()
{
        printf("C program : Started Execution\n");
}

$gcc program.c -o test

also i have a script file named "script" that calls our executable file "test" from the same directory 
and redirecting the output to another temperrory file named "temp.txt"
$vi script

#!/bin/bash

echo "Script : calling C program from our script\n";
./test > temp.txt

now to execute the script first provide the execution permission for your script:
$chmod u+x ./script

now execute the script:
$./script
Script : calling C program from our script

it will give us echo output but no output from our c program cuz we have already redirected the output
now to see the output check the content of our temperrory file "temp.txt"
$cat temp.txt
C program : Started Execution

hope the concepts are clear, feel free to ask your doubts in comments section.
I'll be happy to get back to you as soon as possible.
