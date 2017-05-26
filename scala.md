## Immutable

- Concurrency friendly
- Flow is linear

```
val foo: String = "Mauricio"
```

## Type inference

Let the compiler figure out the types

```
val foo = "Mauricio"
#=> foo: String = Mauricio

val listOfInts = List(1, 3, 2)
#=> listOfInts: List[Int] = List(1, 3, 2)
```

## Functional

- Don't iretate & mutate, transform!
- Define functions in any scope
- Pass functions

```
val f = (s: String) => s.length
#=> f: String => Int = <function1>

```

Another way to define a function

```
def f(s: String): Int = s.length
#=> f: (s: String)Int

List("Mauricio", "Serna", "Florez").map(f)
#=> res4: List[Int] = List(8, 5, 6)

```