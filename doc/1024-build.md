# Building the MinCaml compiler on Mac

1. Add the following line at the head of `Makefile`

    > OCAMLMKTOP = -w -31

1. Add the following line at the head of `float.c`

    ```
#ifdef __APPLE__
typedef int int32;
#endif
```

 typedef int int32

1. `./to_x86`

1. `make`

Now you should get the compiler (`min-caml`) and a custom OCaml interpreter (`min-caml.top`) that can load MinCaml system.

## A file loader utility

Save the following lines as `src/loadall.ml`.  This is a script for loading all the necessary MinCaml definition to an OCaml interpreter.

```
#load "type.cmo"
#load "id.cmo"
#load "m.cmo"
#load "s.cmo"
#load "syntax.cmo"
#load "parser.cmo"
#load "lexer.cmo"
#load "typing.cmo"
#load "kNormal.cmo"
#load "alpha.cmo"
#load "beta.cmo"
#load "assoc.cmo"
#load "inline.cmo"
#load "constFold.cmo"
#load "elim.cmo"
#load "closure.cmo"
#load "asm.cmo"
#load "virtual.cmo"
#load "simm.cmo"
#load "regAlloc.cmo"
#load "emit.cmo"
#load "main.cmo"
```

## Using the MinCaml interpreter

```
bash>  src  ./min-caml.top
        OCaml version 4.03.0

# #use "loadall.ml";;

# let l = Lexing.from_string "let x = 2 in print_int x";;

val l : Lexing.lexbuf =
  {Lexing.refill_buff = <fun>; lex_buffer = "let x = 2 in print_int x";
   lex_buffer_len = 24; lex_abs_pos = 0; lex_start_pos = 0; lex_curr_pos = 0;
   lex_last_pos = 0; lex_last_action = 0; lex_eof_reached = true;
   lex_mem = [||];
   lex_start_p =
    {Lexing.pos_fname = ""; pos_lnum = 1; pos_bol = 0; pos_cnum = 0};
   lex_curr_p =
    {Lexing.pos_fname = ""; pos_lnum = 1; pos_bol = 0; pos_cnum = 0}}

# let e = Parser.exp Lexer.token l;;

val e : Syntax.t =
  Syntax.Let (("x", Type.Var {contents = None}), Syntax.Int 2,
   Syntax.App (Syntax.Var "print_int", [Syntax.Var "x"]))

# Typing.f e;;

free variable print_int assumed as external
- : Syntax.t =
Syntax.Let (("x", Type.Int), Syntax.Int 2,
 Syntax.App (Syntax.Var "print_int", [Syntax.Var "x"]))
```
