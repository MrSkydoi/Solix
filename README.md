please do not purposely steal and redistribute this,
by just using this makes my day.


===================================================
 ______     ______     __         __     __  __    
/\  ___\   /\  __ \   /\ \       /\ \   /\_\_\_\   
\ \___  \  \ \ \/\ \  \ \ \____  \ \ \  \/_/\_\/_  
 \/\_____\  \ \_____\  \ \_____\  \ \_\   /\_\/\_\ 
  \/_____/   \/_____/   \/_____/   \/_/   \/_/\/_/ 

===================================================

________________________________________________________________________________________________________________________________
|Solix is a programming language is a simple and easy to learn and recognize by using lua syntax and structure for simplicity,  |
|Solix is desined to resemble C for familiarity of C programmers, but with a much simpler syntax and structure.                 |
|Solix is an interpreted language, meaning that it is executed line by line, rather than being compiled into binary.            |
|Solix is currently in pre-alpha stage of development, and is not yet ready for production use.                                 |
|Solix is available for testing and feedback from the community.                                                                |
\_______________________________________________________________________________________________________________________________/


Type: Interpreter
Status: PrePreAlpha
Version: 0.0.1


Syntax:

== General:
- include packages: #{packageName}
there are currently no packages available, but this is the syntax for including packages in the future.
- Comments: --//

== Strings
- string concat operator: {VariableName} .. '{string}'
- Strings: '{string}'

== Variables and Functions:
- boolean variables: var {variableName} = true/false
- null: nil
- string variables: var {variableName} = '{string}'
- int variables: var int {variableName}
- functions: var func({value1}, {value2}, {etc}) {function code} end

== Tables:
- Tables: var {tableName} = {}
- Table insert: table.insert({tableName}, {value1}, {value2}, {etc})
- table call: table.call({tableName}, {value1}, {value2}, {etc})
table.call gets the values from the table based on the parameters passed in. The values are returned in a new table. The first value is accessed with [1], the second value with [2], and so on.
Tables cannot be called directly as tableName(...)


== Logic:
- if statements: if {condition} then {code} end
- else if statements: elseif {condition} then {code} end
- else: else {code} end
- and: {condition1} and {condition2}
- not: not {condition}

== output:
- output/print: print('{string}') or print({variable})
- warn: warn('{string}') or warn({variable})
- error: err('{string}' 1/0 bool) or err({variable} 1/0 bool)
- error boolean: 1 = stop code execution, 0 = continue code execution

== Class:
the first class MUST be named Main
- class calling: class.call({ClassName})
- class: class {ClassName} {class code} class end
- classes must be closed with 'class end'
- classes cant be nested



example:

class Main
    var tableInfo = {} --// This is a table
    var Name = 'solix' --// This is a string
    var int Age = 25 --// This is an int variable
    table.insert(tableInfo, Name, Age)
    var func Greet(Name, Age) --// This is a function
        var Table = table.call(tableInfo, Name, Age) --// This is a table call
        if Table[1] == nil then --// This is an if statement
           warn('Name not found in table.')
        elseif Table[2] == nil then
          warn('Age not found in table.')
        elseif Table[1] ~= nil and Table[2] ~= nil then
          warn('Name and Age found in table.') --// This is a warn statement
        else
          err('Age and Name not found in table.', 0) --// This is an error statement
        end
        print('Hello, my name is ' .. Table[1] .. ' and I am ' .. Table[2] .. ' years old.') --// This is a print statement
        
    end
    Greet(Name, Age) --// This is a function call
    class.call(SecondClass) --// This is a class call
class end

class SecondClass
    var func SayHello() --// This is a function
        print('Hello from the second class!') --// This is a print statement
    end
class end
