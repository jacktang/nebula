<!--
# Expression Syntax
The grammar shown here is based on the content in parser/parser.yy file of Nebula source code.

```
%type <expr> expression logic_or_expression logic_and_expression
%type <expr> relational_expression multiplicative_expression additive_expression
%type <expr> unary_expression primary_expression equality_expression
%type <expr> src_ref_expression
%type <expr> dst_ref_expression
%type <expr> input_ref_expression
%type <expr> var_ref_expression
%type <expr> alias_ref_expression
%type <expr> vid_ref_expression
%type <expr> vid
%type <expr> function_call_expression
```

-->