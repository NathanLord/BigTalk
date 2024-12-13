Uses Ohm.js

serializedGrammar

	^'BigTalk {

    Program
    	= "program" Variables? Methods? "do" Statement
    
    Variables
        = "variables" VariableDeclaration+
        
    Methods
    	= "methods" MethodDeclaration+

	VariableDeclaration
        = identifier ":" Type
   
    Type
        = "string"
        | "integer"
        | "boolean"
      
    MethodDeclaration
    	= Function
        | Procedure
        
    Function
    	= "function" identifier ParameterList ":" Type MethodBody
        
    Procedure
    	= "procedure" identifier ParameterList MethodBody
        
    ParameterList
    	= "(" (VariableDeclaration ("," VariableDeclaration)*)? ")"
        
    ArgumentList
    	= "(" (Expression ("," Expression)*)? ")"
        
    MethodBody
    	= Variables? "do" Statement
        
    Statement
   	= CompoundStatement
        | WriteString
	  | WriteInteger
        | WriteBoolean
     	  | WriteLine
        | IfThenElseStatement
        | IfThenStatement
        | AssignmentStatement
        | WhileStatement
        | ProcedureCall
        
    CompoundStatement
    	= "[" Statement+ "]"
        
    WriteString
    	= "writeString" Expression
	
    WriteInteger
       = "writeInteger" Expression

    WriteBoolean
        = "writeBoolean" Expression
        
    WriteLine
    	= "writeLine"
        
    IfThenElseStatement
    	= "if" Expression "then" Statement "else" Statement
        
    IfThenStatement
        = "if" Expression "then" Statement
        
    AssignmentStatement
    	= identifier "<-" Expression
        
    WhileStatement
    	= "while" Expression "do" Statement
 
    UnaryExpression
    	= "NOT" Expression
        
    BinaryExpression
    	= Expression BinaryOperator Expression
    
    Expression
    	= BinaryExpression
	  | FunctionCall
        | UnaryExpression
        | VariableReference
        | literalInteger
        | literalString
        | literalBoolean
        | GroupedExpression
     
    GroupedExpression
    	= "(" Expression ")"
        
	VariableReference
    	= identifier
        
    FunctionCall
    	= identifier ArgumentList
       
    ProcedureCall
       = identifier ArgumentList
       
    literalString
        = "\"" (~"\"" any | "\"\"")* "\""
        
    literalBoolean
    	= "true"
        | "false"
    
    identifier
    	= ~keyword word
        
    BinaryOperator
    	= ArithmeticOperator
        | LogicalOperator
        | RelationalOperator
        
    ArithmeticOperator
       	= "*"
        | "/"
        | "MOD"
        | "+"
        | "-"
        
    LogicalOperator
    	= "AND"
        | "OR"
        
    RelationalOperator
    	= "="
        | "<"
        | ">"
        
    keyword
        = "program"
        | "procedure"
        | "function"
        | "do"
        | "variables"
        | "methods"
        | "if"
        | "then"
        | "else"
        | "while"
        | "writeInteger"
        | "writeString"
        | "writeBoolean"
        | "writeLine"
        | "string"
        | "integer"
        | "boolean"
	  | "true"
	  | "false"
        | "NOT"
        | "AND"
        | "OR"
        | "MOD"
        
    literalInteger
    	= "-"?digit+
        
    word
    	= letter alnum*

}'