# FUNCTIONAL PROGRAMMING

- Based on lambda calculus, lambda calculus (according wikipedia) is a formal system in mathematical logic for expressing computation based on function abstraction and application using variable binding and substitution

*Functional programming is all about programming with functions*
*Input x -> Function f: -> Output f x*

+ Advantages
  * Functional languages can manage concurrency and parallelism
  * Readable
  * Refactoring
  * Easy to test and find bugs

+ Key words in functional programming
  * Immutability
    - No variables, use values
  * Referential
  * Transparency
  * Tail-Call
  * First-class function
  * Optimisation
  * Pattern matching
    - We can define diffent behaviors for the same function

    ```elixir
      factorial 0 = 1
      factorial n = n * factorial(n - 1)
    ```
  * Lambda
  * Purity
  * Side effects
  * Monad (Haskell)
  * Functor
  * Closure
  * High order function
    - All privileges
    - Functions can get other functions as parameters
  * Pure functions
    - Functions without side effects, like math functions
    - For the same input, functions will always the return the same output
    - Result of any call to a function is determined by its arguments
    - Pure functions don't depend on global variables
    - Features:
      + Composability
      + Can run in parallel, multi thread, multi core, distributed system

    ```elixir
      square = fn x -> x * x end
    ```
  * Lists
    - Homogenous data structures
    - We can use map, filter and reduce on lists

- Genservers: Can be used to save states
- Genevents: Model to management events
- Metaprogramming: Capacity to create code in compiling time

+ Hybrid languages
  * Provides multiple abstractions
  * Requires discipline and training
  * Example: Java, Scala, Ruby
+ Constrained, Pure functional languages
  * Provides fewer abstraction
  * Easy to do it right, even without much experience
  * Example: Elixir, Erlang, Haskell, Elm 

## What? Why? When?

## References

+ Codies: Introducción a la programación funcional con elixir y haskell -https://www.youtube.com/watch?v=YGvlViH1umM&list=PLXyl4fuSY_Djhb88ZzW6f8gGjpFlMjQU-&index=1
+ Robert C Martin - Functional Programming; What? Why? When?
https://www.youtube.com/watch?v=7Zlp9rKHGD4
