# Smith
Smith is a Block based programming lanquage primarily made to be the source code of BooneOS.

**⚠️ Notice!** Smith is still in the development stage, because BooneOS is dependant upon it version 1 is expected to be released before 2027.

## Overview

Smith sytnax is extremely simple, it has two variatios one fore libraries and one for actual smith scripts. Smtih program files use the extension **.sm** and uncompiled library compiles use **.sml**. Smith library files are compiled into **Slabs** wich contain the command definitions along with the compiled binaries for the assembly or smith code those command define. Every line of smtih is a command and uses a consistant structure.

### Command(L)/M(A)

All lines have a capitilized **Command** the first word of the line followed by a **letter** in (). The letter selects a set of **modifyers** for that command. Each modifier is followed by a number of argument boxes () which contain content specific to that modifier. 

Here is an example smith program file:

**Import(L)/ID(print)/F(~/path/to/library.slab)**    
**Print(T)/T(Hello)/L(-1)/C(255,0,0)**   
**Input(T)/V(Variable)/M(Who are you: )/L(-1)/C(0,255,0)**  
**Print(V)/ID(Variable)/L(0)/C(0,0,255)**  

This simple program asks the user to input their name and then prints it back out. The firest line imports the **.slab** file which contains the definitions and binaries for the definied assembly in the library. The second line creates a string variable under the name Variable. The third line prints Hello then sets the line position and color. The fourth line uses the Input command definied in the slab to print Who are you: and wait for user input which is saved to Variable. The final line prints the contents of Variable "The users name" and the program ends.

Below is the same script but in **Python** Notice how it is longer and less compact then the above smith script.

import sys  
def print_color(text, r, g, b):  
    sys.stdout.write(f"\033[38;2;{r};{g};{b}m{text}\033[0m\n")  
print_color("Hello", 255, 0, 0)  
sys.stdout.write("\033[38;2;0;255;0mWho are you: \033[0m")  
Variable = input()  
print_color(Variable, 0, 0, 255)  


For a more complex definition of smith syntax refer to the other files in the repo.

## Version 1 Progress

Progress 75%[█████████████████░░░░░]

Smith is in the near ready stage, fully bootstrapped compilers for both .sml files and .sm files exist and are mostly functinal. Final preperations include combining them into a single executable and doing rigerous debug testing. After I have a stable starter compiler i will release it as a demo version for testing and sytnax exploration.




