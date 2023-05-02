# Understanding homoiconic

"defining" homoiconic to mean that it's easy to manipulate programs? More
specifically, say a programming language is homoiconic if (1) the standard
library for the language includes a parser, and (2) the parser returns data
structures that are easily manipulated by functions in the standard library.

Point (2) can be achieved by having the parser return generic data structures
such as lists, arrays and hashtables for which the standard library will
probably have lots of convenient functions (this what Lisps do); or by having a
dedicated AST data type, but including a bunch of AST manipulation functions in
the standard library (like Template Haskell).

Of course, this isn't a very precise definition because it relies on the
undefined terms "parse" and "easily manipulated". Does read_file_to_string()
count as a (trivial) parser that produces strings, which can be easily
manipulated by standard string functions? The idea is this doesn't count, but
I'll leave the problem of defining what counts as a parser to other
philosophers of programming languages.

Unless I’m missing something, there should be (3) these structures can be
passed for evaluation immediately at runtime, linked to that runtime, including
access to current activation record’s data, global symbols and so on. Without
that, (1,2) is simply an ast transformer, and as far as I understand it,
doesn’t count.

## References
