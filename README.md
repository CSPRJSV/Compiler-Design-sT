# Compiler-Design-sT
# VX: csprojhelp 备注: github
sT: A Simple Turing Programming Language 专业辅导

Your assignment is to write a scanner for the sT language in lex. This document gives the lexical definition of the language, while the syntactic definition and code generation will follow in subsequent assignments.

Your programming assignments are based around this division and later assignments will use the parts of the system you have built in the earlier assignments. That is, in the first assignment you will implement the scanner using lex, in the second assignment you will implement the syntactic definition in yacc, and in the last assignment you will generate assembly code for the Java Virtual Machine by augmenting your yacc parser.

This definition is subject to modification as the semester progresses. You should take care in implementation that the programs you write are well-structured and easily changed.

1

Character Set

sT programs are formed from ASCII characters. Control characters are not used in the definition of the language.

2

Lexical Definitions

Tokens are divided into two classes: tokens that will be passed to the parser and tokens that will be discarded by the scanner (i.e. recognized but not passed to the parser).

2.1 Tokens That Will Be Passed to the Parser

The following tokens will be recognized by the scanner and will be eventually passed to the parser:

Delimiters

Each of these delimiters should be passed back to the parser as a token.

dot comma colon semicolon parentheses square brackets brackets

.

, :

; ( ) [ ] { }

1 Arithmetic, Relational, and Logical Operators Each of these operators should be passed back to the parser as a token.

addition subtraction multiplication division remainder assignment relational logical

+ * / mod :=

<

<=

>=

>

=

not=

and or not

Keywords The following keywords are reversed words of sT (Note that the case is significant):

array begin bool char const decreasing default do else end exit false for function get if int loop of put procedure real result return skip string then true var when Each of these keywords should be passed back to the parser as a token.

Identifiers An identifier is a string of letters and digits beginning with a letter. Case of letters is relevant, i.e. ident, Ident, and IDENT are different identifiers. Note that keywords are not identifiers.

Numerical Constants A numerical constant is a sequence of one or more digits and optionally followed by a dot and a sequence of one or more digits.

String Constants A string constant is a sequence of zero or more ASCII characters appearing between double-quote (”) delimiters. A double-quote appearing with a string must be written twice. For example, ”aa””bb” denotes the string constant aa”bb.

2.2 Tokens that will be discarded

The following tokens will be recognized by the scanner, but should be discarded rather than passing back to the parser.

Whitespace A sequence of blanks (spaces), tabs, and newlines.
