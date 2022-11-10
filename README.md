
# Ultraviolet

Ultraviolet is a Scala to GLSL transpiler built using Scala 3's inline macro system.


Notes and limitations:

- GLSL does not support recursion
- GLSL does not support product types, it does allow you to set multiple 'out' values from functions, but for now, we're limited to functions that return a single simple datatype.
- GLSL supports for loops, but we have no way to represent the traditional 'for loop' in Scala, and 'for expressions' are pure syntactic sugar. So no for loops.
- Imports work for free, but only if the things you're importing are inlined, which comes with the usual caveats.
- Pattern matching emulates switch statements, but they are side effecting, not used for setting `val`s.
- If statements are side effecting and cannot set a variable or function return type.
