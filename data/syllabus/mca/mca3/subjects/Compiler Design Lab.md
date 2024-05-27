## Compiler Design Lab

### LAB. ASSIGNMENTS

__LEXICAL ANALYSIS__

`1`.Write a Lex program, which: Given an input C-program, outputs a stream of tokens (other
than blank, tab, \n) on the screen. Output should be of the form: <lineno>: <token_name>
<OPTIONAL token_attribute> As discussed, there are FIVE categories of tokens:

a) Keywords (e.g. for, while, if, char, int etc.):
- Each keyword should be given a separate token_name.
- No token_attribute
- There are 32 keywords in C-language.

b) Operators (e.g. +, ++, +=, etc.)
- Each operator should be given a separate token_name.
- No token_attribute

c) Punctuation marks (e.g. {, }, (, ) etc.)
- Each keyword should be given a separate token_name.
- No token_attribute

d) Identifiers (e.g. name of functions, variables etc.)
- Common token_name = IDENTIFIER
- token_attribute: actual identifier string

e) Constants
 
1: Whole numbers (positive only, as negative sign should be classified as an operator)
- Common token_name = NUMBER
- token_attribute: actual number

2: Real numbers (e.g. 12.34)
- Common token_name = REAL_NUMBER
- token_attribute: actual number

3: Exponential numbers (e.g. 12.34e+56.78)
- Common token_name = EXP_NUMBER
- token_attribute: actual number

4: Character constants (e.g. 'A')
- Common token_name = CHAR_CONSTANT
- token_attribute: actual character

5: String constants (e.g. "ABC")
- Common token_name = STRING_CONSTANT
- token_attribute: actual string



`2`.Write Lex programs for the followings.

i) Checking the number of a’s in words generated over {a, b} is divisible by 2 or not

ii) Counting number of vowels in a text.

iii) Counting number of characters, words, lines in a text

`3`.Write a Lex program for: Given an input C-program (argv[1]), remove all comments, and output a
program (argv[2]) without comments. You have to handle all FIVE types of comments:

(1) 
```
// Single line comment
```

(2) 
```
/* Multi line comment */
```

(3) 
```
/* Nested-1:

// Single line comment within a Multi line comment

*/
 ```

(4) 
```
/* Nested-2:

/* Multi line comment within */

another Multi line comment

 */
```
<span style="color:red">Comment</span> Does not work!!

• If you mean comments of the form `/* . . . */` then the answer is no. Logically, everything
from `/*` is ignored except the first occurrence of `*/`. If a `/*` is encountered inside of the
comment then that is also ignored so the matching `*/` will prematurely terminate the
outside comment.

Logically, it is one kind of pattern matching problem where the concept of extra memory (Stack
) is necessary which is <span style="color:red">not</span>  allowed in FA.

• Comments of the form `// . . .` are terminated by the end of the line so an additional `//`
within that comment will not affect the comment.

(5) `// Nested-3: /*` Multi line comment with a single line comment
 flowing to next line `*/`

Step-1: Figure out the behaviour first. (1), (2) are straight forward. You need to discover how (3)-
(5) behave. It may(?) happen that some lines are not deleted!

Step-2: Give the output file, which removes the comments according to rule you discover in
Step-1.P


__PARSING__

`4`.Build parsers (using YACC OR BISON) for the following languages.
 
i) L={a<sup>n</sup>b<sup>n</sup> | n≥1 } over {a, b}.

ii) L(G) where rule set of G is { S → aSb, S → bSa, S → c } over {a, b, c}

`5`.Build parser (using YACC/BISON) for the following:

i) Converting Infix expression to Postfix expression.

ii) Designing a simple CALCULATOR

iii) Verifying declaration statement of C-language

iv) Verifying multiple assignment statement in C-language

v) Verifying for loop construct in C- language


`6`.Design expression grammar for C-language and write code to generate `ABSTRACT SYNTAX TREE USING YACC`

`7`.Using Lex and YACC tools, write a program to convert infix expression like,
`(a+5)*b+(c-6)/d` into __postfix__ expression.

`8`.Construct a Symbol Table for all the identifiers appearing in the input C-program.