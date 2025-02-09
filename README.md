# MiniC-Compiler

## Grammar

```ebnf
(* Syntactic Grammar for MiniC *)
Program        ::= Stmt*

Stmt           ::= IfStmt
                | Expr
CompoundStmt   ::= '{' Stmt* '}'

Expr           ::= DeclExpr ';'
                | AssignExpr ';'
DeclExpr       ::= Types 'IDENTIFIER' (AssignExprTail)?
Types          ::= 'int' 
                 | 'float'
                 | 'char'
AssignExpr     ::= 'IDENTIFIER' AssignExprTail
AssignExprTail ::= '=' ArithExpr 
ArithExpr      ::= Atom (('+' | '-') ArithExpr)?
Atom           ::= 'INTEGER'
                 | 'FLOAT'
                 | 'IDENTIFIER'
                 | '(' ArithExpr ')'
ExprBool       ::= Atom (OpBool ArithExpr)*
OpBool         ::= '>'
                 | '<'
                 | '>='
                 | '<='
                 | '!='
                 | '=='
IfStmt         ::= 'if' '(' ExprBool ')' CompoundStmt
```
## License
GNU GPL Version 3

**Free Software, Hell Yeah!**
