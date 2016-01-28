## Modern Compiler Construction in Java

#### Chapter 2 - Lexical Analysis

* A Lexical token is a sequence of characters that can be treated as a unit in the grammar of a programming language.

| Type | Examples |
|------|----------|
| ID   | foo  n14 |
| NUM  | 73 0 00 515 |
| REAL | 66.1 .5 10. 5.5e-10|
| IF   | if |
| COMMA | , |
| NOTEQ | != |
| LPAREN | ( |
| RPAREN | ) |

Given a program such as the lexical analyzer will return the stream.
	
	float match0(char * s){
		if (!strncmp(s, "0.0", 3))
			return 0.;
	}


	FLOAT ID("match0") LPAREN CHAR STAR ID("s") LBRACE IF LPAREN BANG ID("strncmp") 
	LPAREN COMMA STRING("0.0") COMMA NUM(3) RPAREN RPAREN ID("return") REAL(0.) SEMI 
	RBRACE EOF

* Some tokens such as identifiers and literals have semantic values attached to them giving auxiliary information in addition to token type.
* In order to specify the lexical tokens formally regular expressions are used.
* In order to implement the lexers DFAs are used.

| Regular Expression Notation | Description |
| ----------------------------|-------------|
| a | An ordinary character stands for itself|
| epsilon | Empty String |
| M  + N | Alternation, choosing M or N |
| M . N | Concatenation, M  followed by N |
| MN | Another way to represent conactenation |
| M* | Repetition, zero or more times |
| M+ | Repetition , one or more times |
| M? | zero or one occurence |
| [a-zA-Z] | Character set Alternation |

* Rule priority: For a particular longest initial substring, the first regular expression that can match determines its token type. This means
that order of writing down the regular expression rules has significance.