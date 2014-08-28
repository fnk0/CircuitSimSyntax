#### CircuitSimSyntax
====================

Small syntax plugin for circuitSim to be used with Sublime Text. 
CircuitSim is a java program to simulate circuits at gate level writen by Dr. David Cline to be used on his Computer Systems class @ Oklahoma State University.

#### Usage

Create a folder inside the packages folder with the desired name for the syntas such as CircuitSim
Download the .tmLanguage file and place inside the created folder.

To enable the Syntax Highlight feature save a file as ````.csim```` or inside subline go to View -> Syntax -> CircuitSim

#### Auto Complete

I've also added some auto complete feature for the keywords. The auto complete is accomplished by pressing TAB 
Ex: if you type "in" and press TAB would generate inputNames { }

To use the auto complete feature place the file CircuitSimCompletions.sublime-completions inside the root of the packages folder. 

#### Using .csim files

If you wish to save your files as .csim so Sublime automatic detects the Syntax you can use the runScript as to convert the .csim files to .txt files and run the program with the newly created .csim file.

By example:

Let's suppose you have a folder named foo with the CircuitSim.jar file and a OR.csim file. Your structure would look like something like this:

```
  foo/
    CircuitSim.jar
    OR.csim
```
to run the script using .csim files you would use: ```runScript OR```
Arguments can also be used with this script such as: ```runScript OR 1```

The script will generate a folder called out with the new txt files and with the CircuitSim.jar copied to the new directory. The copy command is only executed if the ```out``` folder does not already have the .jar file.

Your directory structure now would look like this:

```
  foo/
    out/
      CircuitSim.jar
      OR.txt
    CircuitSim.jar
    OR.csim

```

You can use the .txt file as a working backup of your .csim file in case you mess something up :)

Alternativally the runScript can be used with the argument ``` -cp ``` to only convert the files without executing the program. 

##### Converting ALL files in a directory from ```.csim``` to ```.txt``` 

``` runScript -cp * ```

####### Running runScript from anywhere

UNIX: copy the runscript to the /usr/bin folder --> sudo cp runScript /usr/bin 

Windows: Add the runScript to your PATH variable. 


#### Circtuit Sim Syntax Specs
###### Keywords
````
  inputNames
  outputNames
  circuit
  outputs
  truthTable
  propagationDelay
  circuitInputs
  testCase
````
###### Convention / Common File names to be used
````
  AND
  NAND*
  XOR
  OR
  NOT
  NOR
  HALF-ADDER or HalfAdder
  ADDER or Adder
  FULL-ADDER or FullAdder
  SELECTOR
  MULTIPLEXOR
  PASSTHROUGH
  WIRE
  DECODER
  MUX
  ALU
  SEKECT
  T_SELECT
  SHIFT_CONTROL_SELECT or ShiftControlSelect
  SHIFT_LEFT or ShiftLeft
  SHIFT_RIGHT or ShiftRight
  OUTPUT_SELECT or OutputSelect
  MAJORITY
  MINORITY
  CARRY-SELECT-ADDER or CarrySelectAdder
  RIPPLE_CARRY_ADDER or RippleCarryAdder
  
````
###### Common Punctuation
  * Boolean Control
````
    ^
    ~
    &
    |
    !
````
  * Structure Control
````
    {}
    []
    ()
````
  * Other Punctuation
````
    =
    ,
    :
    .
````

Enjoy :)

