# fp2016
Functional Programming for Year 2016

Date | Content | Assignment
----- | ----- | :-----:
Sep. 26 | [Overview](01-overview.md) | Reading assignment & Install OCaml on your laptop
Sep. 29 | [Introduction to functional programming in OCaml (1)](02-ocaml1.md) | Assignment is placed on OCW-i
Oct. 3 | [Introduction to functional programming in OCaml (2)](02-ocaml1.md) |
Oct. 6 | [Min-Caml compiler organization](04-mincaml.md) |
Oct. 13 | [Lexer and parser](doc/1013.md) |
Oct. 17 | [Type system](slides/oct17.pdf) |
Oct. 20 | KNF, Beta, Alpha, maybe more | [Reading assignment](https://en.wikipedia.org/wiki/Unification_(computer_science))

# Agenda

Date | Theory | Implementation |
----- | ----- | -----
oct17 | Typing                 ||
oct20 | KNF , Alpha            ||
oct24 | Beta, Assoc, Inline    | Typing (Nagayama Kanato) |
oct27 | ConstFold, Elim        | KNF (Osako Kayo), Alpha (Soga Mitsuaki) |
oct31 | Closure conversion     | Beta (Sarocha Sothornprapakorn), Assoc (Anthony Dubucq), Inline (Ling Tan) |
nov3  | Virtual machine code   | ConstFold (Mark Bo Jensen, Zhengqing Li), Elim (Jonathan Golan) |
nov7  | (SIMM is skipped) Register Allocation | Closure conversion (Inukai Yasuhiro) |
nov14 |                        | Virtual machine code, SIMM |
nov21 |                        | Register Allocation (Dashdemberel Batchunag) |

# References

## About OCaml

- [The OCaml system release 4.03: Documentation and user's manual](doc/ocaml-4.03-refman.pdf)

## About MinCaml

- [The MinCaml compiler stages](doc/mincaml-overview.pdf), a semi-formal description

- E. Sumii, [MinCaml: A simple and efficient compiler for a minimal functional language](doc/sumii-05-mincaml-paper.pdf), FDPE '05, 2005

- E. Sumii, [MinCaml: A simple and efficient compiler for a minimal functional language](doc/sumii-05-mincaml-slide.pdf), slideware presented at FDPE '05, 2005

- [A micro overview of the MinCaml project](doc/sumii-04-overview.pdf) (in Japanese)


- [MinCaml project summary report](doc/sumii-mincaml-final-report.pdf)

## Others

- On type system  
Benjamin Pierce, [Types and Programming Languages](https://www.amazon.co.jp/dp/B00AJXZ5JE), MIT Press, 2002.

<!--
Class 2	Introduction to functional programming in OCaml (1)	 Primitive data types, compound data types, algebraic data types. 
Class 3	Introduction to functional programming in OCaml (2)	 Recursive data structures, recursive functions, higher-order functions, mutable states. 
Class 4	Introduction to functional programming in OCaml (3)	 Records, exception handling, modules, standard library, tools
-->
