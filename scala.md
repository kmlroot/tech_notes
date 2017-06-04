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
- Pass functions to other functions

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

List("Mauricio", "Serna", "Florez").map(s => s.length)
#=> res5: List[Int] = List(8, 5, 6)

List("Mauricio", "Serna", "Florez").map(_.length)
#=> res6: List[Int] = List(8, 5, 6)
```

## Expression oriented

- Expressions: COmbination of symbols that represent a value
- Unit is a value
- Very few "statements" in Scala

```
class Foo
#=> defined class Foo

def f(s: String) = {
  val i = s.length
  i
}

f("Mauricio")
#=> res7: Int = 8

val i = if(true) "foo" else "bar"
#=> i: String = foo

val i = if(false) "foo" else "bar"
#=> i: String = bar
```

## Pattern matching

- Expressions that match on something
- More technically: Partial function applied to any value

```
trait Blah

class Foo extends Blah
class Bar extends Blah

val b: Blash = new Foo

b match {
  case bar: Bar => "bar"
  case foo: Foo => "foo"
}

val pf: PartialFunction[Any, String] = {
  case foo: Foo => "Mauricio"
}

pf.isDefinedAt("Mauricio")
#=> res1: Boolean = false

val foo = new Foo

pf.isDefinedAt(foo)
#=> res2: Boolean = true

List(1, "Mauricio", foo).collect(pf)
#=> res4: List[String] = List(Mauricio)
```

## Case classes

- Concise syntax for value objects
- Built-in toString, equals, hash-code, extractor, creattor, copy

```
case class Foo(name: String)

new Foo("Mauricio")
#=> res5: Foo = Foo(Mauricio)

Foo.apply("Serna")
#=> res6: Foo = Foo(Serna)

res6.copy(name = "Alba")
```

## For comprehensions

```
val m1 = Some("Mauricio")
val m2 = Some("Serna")

m1.flatMap(mm1 => m2.map(mm2 => mm1 + mm2))

for {
  mm1 <- m1
  mm2 <- m2
} yield mm1 + mm2
```

## Reactive

- Futures
- Actors
- Non-blockingIO

## Monad

The fundamentalist functional approach would mandate that typer state is represented as a monad.

Instead of now:

```
def typed(tree: untpd.Tree, expected: Type): tpd.Tree
def isSubType(tp1: Type, tp2: Type): Boolean
```

Write:

```
def types(tree: untpd.Tree, expected: Type):
  TyperState[tpd.Tree]

def isSubType(tp1: Type, tp2: Type):
  TyperState[Boolean]

```

Instead of now:

```
if (isSubType(t1, t2) && isSubType(t2, t3)) result
```

Write:

```
for {
  c1 <- isSubType(t1, t2)
  c2 <- isSubType(t2, r3)
  if c1 && c2
} yield result
```

## Modules

Modules can take a large number of forms

- A function
- An object
- A class
- An actor
- A stream transform
- A microservice

## References

- [SF Scala: Martin Odersky, Scala -- the Simple Parts](https://www.youtube.com/watch?v=ecekSCX3B4Q)
