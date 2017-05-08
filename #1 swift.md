#1 swift



Why was the language created?

Swift is a general-purpose, multi-paradigm, compiled programming language developed by Apple Inc. for iOS, macOS, watchOS, tvOS, and Linux.  Swift was created as an upgrade to Objective C, by being more concise and safer.

Some of the problems that Swift tries to address is that it does not expose pointers and other unsafe accessors.  Swift also tries to make their code cleaner by utilizing inferred types and modules to eliminate headers and provide namespaces, as well as using simple three-character keywords to define a variable.  Another reason is that by defaullt Swift objects can never be nil.  Optionals are used to coincise with this built in feature, and enables you to test for nil.  You don't need to type semi colons and memory is also managed.



---------------------------------


Is the language a reaction to a previous language or a replacement for another language?

A big reason of creating swift was to make objective c safer.

----------------------------------

How are Namespaces used?

Namespacing in Swift is implicit, meaning that all classes are implicitly scoped by the module that they are in.  You can reuse names that are in the same scope.


----------------------------------

What types are used?

Swift allows you to use Int or UInt, Float, Double, Bool, String, Character and Optional.

Can you use value or reference types?

Swift provides value and reference types.  Value types are where each instance keeps a unique copy of its data, usually defined as a struct, enum, or tuple.  The second, "reference types", are where instances share a single copy of the data, and the type is usually defined as a class.

Swift also allows multiple return values which allow  you to return a tuple of data from a function

an example
func getTime() -> (Int, Int, Int){
    ...
    return ( hour, minute, second)
}

// Value type example
struct S { var data: Int = -1 }
var a = S()
var b = a						// a is copied to b
a.data = 42						// Changes a, not b
println("\(a.data), \(b.data)")	// prints "42, -1"

// Reference type example
class C { var data: Int = -1 }
var x = C()
var y = x						// x is copied to y
x.data = 42						// changes the instance referred to by x (and y)
println("\(x.data), \(y.data)")	// prints "42, 42"



--------------------------------
Classes

*Defining*

Defining a class in swift is shown below

class ExampleClass{

}


when you use variables you will need to deine the type.  You will use let to define a constant and then an init to show the order in which the variables will be initialized.  You usually not have to write self in your code very often because Swift assumes that you are referring to a property or method of the current instance whenever you use a known property or moethod name within a method.  It is the same as the keyword 'this' in Java. ? is an optional

class Person {
	let name:String
	var nickname:String?
	var age:Int

	init(name:String,nickname(String? = nil),age:Int){
		self.name = name
		self.age = age
		self.nickname = nickname
	}
}

Defining a class in Java is shown below and is the same as swift

class MyClassName{
    ...
}

A class is the blueprint from which individual objects are created

----------------------------------
*Creating new Instances*


var personOne = Person(name: John, age: 20, nickname: JDog)


class Mutant:Person{
	var level:Int
	var superPower:String

	init(name:String, age:Int, superPower:String,nickname: String? = nil){
		self.level = level
		self.superPower = superPower
		super.init(name:name, age: age, nickname: nickname)

		}

		func isMorePowerful(mutant:Mutant) -> Bool{
			return (level > mutant.level)
		}
}

var jim = Mutant(name: "Jim Neutron", age:23, level: 7, superPower"Flight", nickname: "Flyin Jim")

var janet = Mutant(name:"Janet Jackson", age:32, level:8, superPower: "Telepathy", nickname:"The great one")

janet.isMorePowerful(jim)

class SomeClass {
	class func typeMethod(#string:String) -> String{
	return string + "_ModifiedInClassMethod"
	}
}

in other classes this would be static

var strToModify:String = "Happy String"

SomeClass.typeMethod(string: strToModify)


---------------------------------

Properties

Properties associate values with a particular class, structure, or enumeration.  Stored properties store constant and variable vlaues as port of an instance.

struct Point
{
	var x = 0.0, y = <0.0
}

struct Size
{
	var width = 0.0, height = 0.0
}

struct Rect
{
	var origin = Point()
	var size = Size()
	var center: Point
	{
	get
		{
		let centerX = origin.x + (size.width / 2)
		let centerY = origin.y + (size.height / 2)
		return Point(x: centerX, y: centerY)
		}

	set(newCenter)
		{
		origin.x = newCenter.x - (size.width / 2)
		origin.y = newCenter.y - (size.height / 2)
		}
	}

var square = Rect(origin: Point(x:0.0, y:0.0),size: Size(width:10.0, height:10.0))
let initialSquareCenter = square.center
square.center = Point(x: 15.0, y: 15.0)

}


----------------------------------------------------------
Protocols vs Interface in Java



Protocols are very similar to Java interfaces except for:

	Swift protocols can also specify properties that must be implemented

	Swift protocols need to deal with value/reference through the use of the mutating keyword (because protocols can be implemented by structs and classes)

	you can combine protocols at any point with the protocol<> keyword. For example, declaring a function parameter that must adhere to protocol A and B as:

	func foo ( var1 : protocol<A,B>){

	}


	swift protocol magic comes from extensions

	swift protocols can get implementations via extensions


-----------------------------------------------------------

Swift uses a technology called Automatic Reference Counting to allocate and deallocate memory for you

For Java when the heap becomes full, garbage is collected.  During the garbage collection objects that are no longer used are cleared, thus making space for new objects.


-----------------------------------------------------------

Comparison of references and values

Swift Comparison Operators

Equal to (a == b)
Not equal to (a != b)
Greater than (a > b)
Less than (a < b)
Greater than or equal to (a >= b)
Less than or equal to (a <= b)

1 == 1   // true because 1 is equal to 1
2 != 1   // true because 2 is not equal to 1
2 > 1    // true because 2 is greater than 1
1 < 2    // true because 1 is less than 2
1 >= 1   // true because 1 is greater than or equal to 1
2 <= 1   // false because 2 is not less than or equal to 1


-----------------------------------------------------------

Null/nill references

Swift uses nill Java uses null

Java does not have implicit optionals while Swift has in-built optionals

-----------------------------------------------------------

In Swift, errors are represented by values of types that conform to the Error protocol.

example

class CreditCard
{

    let creditLimit = 1000
    var creditBalance = 0.0

    func purchase(let amount:Int)
    {
        if creditBalance + amount > creditLimit{
            fatalError("Could not make the purchase")
        }
        else{
            creditBalance += amount
            print("Your current balance is $\(creditBalance)")
        }
    }
}



-------------------------------------------------------------

Lambda expressions, closures, or functions as types


//In swift there are four kinds of expressions: prefix expressions, binary expressions, primary expressions and postfix expressions
closing expressions are primary expressions

A closure expression creates a closure, also known as a lambda or an anonymous function in other programming languages.  Like a function declaration, a closure contains statements, and it captures constants and variables from its enclosing scope.

{(parameters) -> return type in
statements

}

Another example, the following expressions are equivalent

myFunction {(x: Int, y:Int) -> Int
    return x + y.data
}

myFunction {x, y in
    return x + y
}

myFunction { return $0 + $1}

myFunction { $0 + $1}

-------------------------------------------------------------------


Implementation of Listeners and event handlers











-------------------------------------------------------------------


Singletons

The singleton pattern is a very useful pattern.  There are times that you want to make sure only one instance of a class is instantiated and that your application only uses that instance.  That is the primary and only goal of the singleton pattern.



Swift example

class NetworkManager{

    // MARK: - Properties

    static let shared = NetworkManager(baseURL: API.baseURL)

    // MARK : -

    let baseURL: URL

    // Initialization

    private init(baseURL: URL){
        self.baseURL = baseURL
    }


}

The initializer of global variables and static properties are executed lazily by default.


class TheOneAndOnlyKraken{
    static let sharedInstance = TheOneAndOnlyKraken()
    private init(){} //this prevents others from using the default '()' initializer for this class.
}


---------------------------------------------------------------------

Procedural Programming

Procedural programming can be defined as a subtype of imperative programming as a programming paradigm based upon the concept of procedure calls, in which statements are structured into procedures.




Swift supports procedural programming and is a multi-paradigm language but is more similar to 



---------------------------------------------------------------------

Functional Programming

The main high level goals for a functional program are modularity, careful treatement of mutable state and in some functional languages extensive usage of types to produce safe, easy to maintain, easy to test and performant code.  Functional programming is a declarative programming style that treats computation as the evaluation of mathematical functions.  Functions are primary units of abstration and base building blocks of a program, in contrast to object oriented paradigm where we have objects as main building blocks.  Essence of functional programming is minimising and controlling side effects.

Swift is certainly not a functional language, but it does use core aspects of functional programming as a corner stone of its vision of how to write safe, easy to maintain and fast code.  Immutability is not just a convention for collections anymore, everything in Swift should be immutable by default.  We declare all our variables with let keyword, and only when really necessary by semantics of the variable we change it to a var.

Functions are first class type in Swift.  This means that in Swift, similarly to what we have in functional languages, functions are data the same 



------------------------------------------------------------------------







