# BigTalk
New language based on Smalltalk.


## Grammar 
[Basics](/BigTalkGrammar.md) for the statically typed structured programming language.

## Parser
[Rules](/BigTalkParser.md) For the parser.

## Setup
### Installing smalltalk code
filein all the .st files


#### Installing Base code
* BigTalk-Errors.st
* BigTalk-Types.st
* BigTalk-Variables.st
* BigTalk-Scopes.st



#### Installing code for Ohm
* Open a Monticello Browser
* Push the '+Repository' button.
* Choose 'directory' for the repository type.
* Navigate to location with the Ohm file and accept.
* Select the new repository in the repository list and push the 'Open' button.
* Select 'Ohm' and 'Ohm-BigTalk.mcz.
* Push the 'Load' button.


#### Installing Cont.

This code will move the class BTType and its children to the system category BigTalk-AST.
* BigTalk-AST.st  (Abstract Syntax Tree)

* BigTalk-Parser.st (Builds the AST)

* BigTalk-Interpreter

* BigTalk-Formatter.st (Formats BigTalk Code)

* BigTalk-CodeGenerator (Writes the translated C code from BigTalk code)

* BigTalk-SemanticAnalyzer (Checks for errors in program)