# Brief Scala Syntax Cheat Sheet

### Table of contents

- **[Syntax representation](#syntax-representation)**
- **[Types](#types)**
- **[Expressions](#expressions)**
- **[Definitions](#definitions)**
- **[References](#references)**

## Syntax representation

**The syntax represented in _Extended Backus-Naur Form (EBNF)_, where:**

```scala
 - | denotes alternative
 - [...] an option (0 or 1)
 - {...} a repetition (0 or more)
```

## Types

```scala
Type = SimpleType | FunctionType

FunctionType = SimpleType '=>' Type | '(' [Types] ')' '=>' Type

SimpleType = identifier

Types = Type {',' Type}
```

**A type can be:**

- A **numeric type**: ```Int, Double (and Byte, Short, Char, Long, Float)```,
- The **Boolean type** with the values ```true``` and ```false```,
- The **String type**,
- A **Function type**, like ```Int => Int, (Int, Int) => Int```

## Expressions

```scala
Expr = InfixExpr | FunctionExpr | if '(' Expr ')' Expr else Expr

InfixExpr = PrefixExpr | InfixExpr Operator InfixExpr

Operator = identifier

PrefixExpr = ['+'|'-'|'!'|'~'] SimpleExpr

SimpleExpr = identifier | literal | SimpleExpr '.' ident | Block

FunctionExpr = Bindings '=>' Expr

Bindings = identifier[':' SimpleType] | '('[Binding {',' Binding}] ')'

Binding = ident [':' Type]

Block = '{' {Def ';'} Expr '}'
```

**Expressions can be:**

- An **identifier** such as ```x, isGoodEnough```
- A **literal**, like ```0, 1.0, "abc"```
- A **function application**, like ```sqrt(x)```
- An **operator application** , like ```-x```, ```y+x```
- A **selection**, like ```math.abs```
- A **conditional expr**, like ```if(x<0) -x else x```
- A **block**, like ```{val x = math.abs(y); x*2}```
- An **anonymous function**, like ```x=>x+1```

## Definitions

```scala
Def = FunctDef | ValDef

FunctDef = def identifier{ '('[Parameters]')' }[: Type] '=' Expr

ValDef = val identifier[':' Type] '=' Expr

Parameters = Parameter{',' Parameter}

Parameter = identifier ':' ['=>'] Type
```

**A definition can be:**

- A **function definition**, like ```def square(x: Int) = x*x```
- A **value definition***, like ```val y = square(2)```

**A parameter can be:**

- A **call-by-value parameter**, like ```(x: Int)```
- A **call-by-name parameter**, like ```(y: => Double)```

## References

> References

```text
Coursera
Martin Odersky.
Functional Programming Principles in Scala
[Online] Available from: https://class.coursera.org/progfun-003
[Accessed: 06 August 2014].

Coursera
Martin Odersky.
Functional Programming Principles in Scala.
Lecture 2.4 - Scala Syntax Summary (4:13).
[Online] Available from:https://class.coursera.org/progfun-003/lecture/41
[Accessed: 06 August 2014].

Scala
[Online] Available from: http://www.scala-lang.org/
[Accessed: 06 August 2014].

Extended Backus–Naur Form
[Online] Available from: http://en.wikipedia.org/wiki/Extended_Backus%E2%80%93Naur_Form
[Accessed: 09 August 2014].

The Scala Language Specification Version 2.9
Martin Odersky.
[Online] Available from: http://www.scala-lang.org/docu/files/ScalaReference.pdf
[Accessed: 10 August 2014].
```
