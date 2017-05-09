Why was the language created?

Swift is a general-purpose, multi-paradigm, compiled programming language developed by Apple Inc. for iOS, macOS, watchOS, tvOS, and Linux.  Swift was created as an upgrade to Objective C, by being more concise and safer.

Some of the problems that Swift tries to address is that it does not expose pointers and other unsafe accessors.  Swift also tries to make their code cleaner by utilizing inferred types and modules to eliminate headers and provide namespaces, as well as using simple three-character keywords to define a variable.  Another reason is that by defaullt Swift objects can never be nil.  Optionals are used to coincise with this built in feature, and enables you to test for nil.  You don't need to type semi colons and memory is also managed.

Java is a general-purpose computer programming language that is concurrent, class based, object oriented.  One of the specific designs that the creators of Java had was, "write once, run anywhere"(WORA), which meant that you would be able to run Java on multiple platforms without having dependecy or platform issues.  The simplicity of object oriented design and its ability to be architecture-neutral as well as having fast compililation made Java become one of the most popular languages in the programming community.

---------------------------------


Is the language a reaction to a previous language or a replacement for another language?

A big reason of creating swift was to make objective c safer and to create a language that would be versatile and simple to learn.

Java was a reaction to OOP becoming the hot trend at the time and needing a language that would be designed for it.


----------------------------------

How are Namespaces used?

Namespacing in Swift is implicit, meaning that all classes are implicitly scoped by the module that they are in.  You can reuse names that are in the same scope.

Packages are namespaces for Java and can be defined as a grouping of related types (classes, interfaces, enumerations and annotations)

ex. java.lang, java.io

----------------------------------

What types are used?

Swift allows you to use Int or UInt, Float, Double, Bool, String, Character and Optional.

Java allows you to use byte, int, short, long, float, double, boolean and char.

-----------------------------------

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


In Java, all objects and enums are reference types, and all primitives are value types.

To declare a variabule using a reference type, you simply list the class name as the data type.

ex.

Cat c;


--------------------------------
Classes

*Defining*

Defining a class in swift is shown below

class ExampleClass{

}


when you use variables you will need to define the type.  You will use the keyword 'let' to define a constant and then an 'init' to show the order in which the variables will be initialized.

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

A class is the blueprint from which individual objects are created.

----------------------------------
*Creating new Instances*

Instantiating in Swift is shown below.

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

A very simple example of instantiating in java is shown below

Cat c = new Cat();

The difference between these two instantiations is that Swift allows you to specify the values in the instantiation and then compares it using a function that is built into the class.

---------------------------------

Properties

Properties associate values with a particular class, structure, or enumeration.  Stored properties store constant and variable vlaues as port of an instance.

Shown below is swift setting properties to structures

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

You can figure out what a property means in Java by using methods.  A few examples are getName(),getPropertyType(), and getReadMethod.


----------------------------------------------------------
Protocols vs Interface



Protocols in swift are very similar to Java interfaces except for:

	Swift protocols can also specify properties that must be implemented

	Swift protocols need to deal with value/reference through the use of the mutating keyword (because protocols can be implemented by structs and classes)

	you can combine protocols at any point with the protocol<> keyword. For example, declaring a function parameter that must adhere to protocol A and B as:

	func foo ( var1 : protocol<A,B>){

	}


	swift protocol magic comes from extensions

	swift protocols can get implementations via extensions


-----------------------------------------------------------

Reflection


Reflection is a language's ability to inspect and dynamically call classes, methods, attributes, etc. at runtime.

Reflection allows for more dynamic programming and lets you write programs that do not have to "know" everything at compile time, making them more dynamic, since they can be tied together at runtime.  Java uses an API to run reflection.


//the object
public class reflectEx extends reflectMain
{
private String idcode = "100";
private String getPrivate(){return "How did you get this";}
private String getOtherPrivate(int thisInt, String thatString){
    return "How did you get here " + thisInt + " " + thatString;
}

public reflectEx(int number, String randString){
    System.out.println("You sent: " + number + " " + randString);
}

CarFactory exFactory

public reflectExCar(CarFactory exFactory)
{
this.exFactory = exFactory;
}

void makeFactory(){
    System.out.println("Making car " + getName());

    wheel = carFactory.addWheel();
    engine = carFactory.addEngine();
}

}
//the reflection api
public class reflectMain{
public static void main(String[] args)
{

    Class reflectClass = reflectEx.class;

    String className = reflectClass.getName();

    System.out.println(className +"\n");

    //check modifiers of a class

    int classModifiers = reflectClass.getModifiers();

    Method[] classMethods = reflectClass.getMethods();

    for (Method method : classMethods)
    {
        System.out.println("Method name: " + method.getName());

        if(method.getName().startsWith("get")){
            System.out.println("Getter Method");
        }
    }

    //accessing class constructors

    Constructor constructor = null;

    Object constructor2 = null;

    try{

        constructor = reflectClass.getConstructor(new Class[]{CarFactory.class});

        constructor2 = reflectClass.getConstructor(int.class, String.class).newInstance(12, "Random String");
    }

    catch (NoSuchMethodException | SecurityException e) {

                // Exceptions thrown
                e.printStackTrace();

            } catch (InstantiationException e) {

                // TODO Auto-generated catch block

                e.printStackTrace();

            } catch (IllegalAccessException e) {

                // TODO Auto-generated catch block

                e.printStackTrace();

            } catch (IllegalArgumentException e) {

                // TODO Auto-generated catch block

                e.printStackTrace();

            } catch (InvocationTargetException e) {

                // TODO Auto-generated catch block

                e.printStackTrace();

            }

            //return the parameters for a constructor

    Class[] constructParameters = constructor.getParameterTypes();

    for (Class parameter : constructParameters){
        System.out.println(parameter.getName());
    }

    ReflectionEx newCar = null;
    CarFactory newCarFactory = null;

    try {
        newCar = (ReflectionEx) constructor.newInstance(carFactory);
    }

    catch (InstantiationException | IllegalAccessException | IllegalArgumentException | InvocationTargetException e){

        e.printStackTrace();
    }
    //now you can call methods in the ReflectionEx Object
    newCar.setName("Honda");

}

}

---------------------------------------------------------

Memory Management

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

In Swift, Equatable is a protocol from which Comparable and hashable are used together.  These protocols form the central point of comparison throughout the language.

For Swift reference types, equality can be evaluated as an identity check on an ObjectIdentifier constructed with an instance of that type:

class Object: Equatable{}

// MARK: Equatable

func ==(lhs: Object, rhs: Object) -> Bool{
    return ObjectIdentifier(lhs) == ObjectIdentifier(rhs)
}

Object() == Object () //false

For swift value types,

extension Complex: Equatable {}

// MARK: Equatable

func ==<T>(lhs: Complex<T>, rhs: Complex<T>) -> Bool {
    return lhs.real == rhs.real && lhs.imaginary == rhs.imaginary
}

let a = Complex<Double>(real: 1.0, imaginary:2.0)
let b = Complex<Double>(real: 1.0, imaginary:2.0)

a == b //true
a != b //false

Java comparison operators
= assingment operator
== equal to
2 > 1    // true because 2 is greater than 1
1 < 2    // true because 1 is less than 2
1 >= 1   // true because 1 is greater than or equal to 1
2 <= 1   // false because 2 is not less than or equal to 1

Java comparison operators are straightforward, however there are some common errors associated with them

ex.
0 < x < 100

is wrong because you need to include an '&' operator since Java comparison operators can only be used with two numbers.

solution.
0 < x && x < 100;

= instead of ==
You can't use the assignment operator to symbolize an equality operator.  This is an syntax error.



-----------------------------------------------------------

Null/nill references

Swift uses nill Java uses null

Java does not have implicit optionals while Swift has in-built optionals

There is no type which null is an instance of in Java.  Null in java is a special literal that can be of any reference type.  In java null == null.  Null is also the default value (for variables that hae them) for all reference types.  This creates many problems for programmers as it is very easy for an object to be referenced a null value and it can be hard to error check.



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

Java uses exceptions to handle their errors.  An exception is a problem that arises during the execution of a program.  When an exception occurs the normal flow of the program is disrupted and the program/application terminates.  A method will catch an exception using a combination of the try and catch keywords.

example

try{
    //code
}catch(ExceptionName e1){
    //catch block
}





-------------------------------------------------------------

Lambda expressions, closures, or functions as types


Swift uses closures instead of lambda expressions.

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

In java Lambda Expressions are used instead of closures.  Lambda expressions allow you to be more specific and make code cleaner.  They are used primarily to define inline implementation of a functional interface.  Lambda expressions get rid of the need for anonymous class and gives a simple but effective functional programming ability to Java.

Lambda Expressions are characterized by the following syntax

parameter -> expression

MathOperation multiplication = (int a, int b) -> a / b;

-------------------------------------------------------------------


Implementation of Listeners and event handlers


Event handlers is an action recognized by the software and is handle according to the code in the event block.  Listeners on the other hand wait for an action to happen and then create an event according to it's code.

An example of Swift event handlers is shown below

class EventHandler: UIApplication{

    override func sendEvent(event:UIEvent){
        super.sendEvent(event)
        print("Some Event")
    }
}

This function prints "some event happened" when a button is clicked.

In Java, an action event is whenever an action is performed by the user.  Action Listeners wait for an action to happen and then respond according to their code.

An example is shown below

public class Beeper ... implements ActionListener {
    ...
    //where initialization occurs:
        button.addActionListener(this);
    ...
    public void actionPerformed(ActionEvent e) {
        ...//Make a beep sound...
    }
}

In this example a button is clicked and creates a beep sound accordingly.


-------------------------------------------------------------------


Singletons

The singleton pattern is a very useful pattern that makes sure only one instance of a class is instantiated and that your application only uses that instance.

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

Singletons can be made to be thread safe in Java.  An example below.

public class ASingleton{

    private static ASingleton instance = null;
    private static Object mutex = new Object();
    private ASingleton(){

    }

    public static ASingleton getInstance(){
        if(instance==null){
            synchronized (mutex){
                if(instance==null) instance = new ASingleton();
            }
        }
        return instance;
    }
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


Multithreading


Java is a multi-threaded programming language which means we can develop multi-threaded program using Java.  A multi-threaded program contains two or more parts that can run concurrently and each part can handle a different task at the same time making optimal use of the available resources specially when your computer has multiple CPUs.



Every Java thread has a priority that helps the operating system determine which threads are scheduled.


Creating a thread by implementing a runnable interface is one way to exucte a thread

example shown below

class RunnableDemo implements Runnable {
   private Thread t;
   private String threadName;
   
   RunnableDemo( String name) {
      threadName = name;
      System.out.println("Creating " +  threadName );
   }
   
   public void run() {
      System.out.println("Running " +  threadName );
      try {
         for(int i = 4; i > 0; i--) {
            System.out.println("Thread: " + threadName + ", " + i);
            // Let the thread sleep for a while.
            Thread.sleep(50);
         }
      }catch (InterruptedException e) {
         System.out.println("Thread " +  threadName + " interrupted.");
      }
      System.out.println("Thread " +  threadName + " exiting.");
   }
   
   public void start () {
      System.out.println("Starting " +  threadName );
      if (t == null) {
         t = new Thread (this, threadName);
         t.start ();
      }
   }
}

public class TestThread {

   public static void main(String args[]) {
      RunnableDemo R1 = new RunnableDemo( "Thread-1");
      R1.start();
      
      RunnableDemo R2 = new RunnableDemo( "Thread-2");
      R2.start();
   }
}

In swift when multitasking there are a couple of options.  One option is using Grand Central Dispatch for these tasks.  A basic example is

let backgroundQueue: dispatch_queue_t = dispatch_queue_create("com.a.identifier", DISPATCH_QUEUE_CONCURRENT)

dispatch_async(backgroundQueue){

}

dispatch_release(backgroundQueue)

Another route could be that you use operation queues.  An example is shown below

let queue = OperationQueue()

queue.addOperation(){


    OperationQueue.main.addOperation(){
        //when finished, update your UI on the main queue
    }
}


