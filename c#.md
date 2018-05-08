C# critera
1) Language purpose/genisis
  * C# was created in 2000 by Anders Hejsberg at Microsoft. There was much rivarly rooted in it's development. Sun (Oracle) who created Java, didn't want Microsoft changing Java. C# was created to enable developers to build applications on the .NET framework and the syntax as well as functionality is very similar to java. This language was developed to make it easier to build apps on the .NET framework. By building these applcations on the .NET framework developers can call the code (in the framework) without writing it, and thus reducing the time it takes to build one of these apps.
2) Unique features of the language
  * One of the main features that attracts many people to C# is the .NET framework. The .NET framework is not only expansive but is periodically updated at a faster rate than Java. This allows c# to shine through as the more up to date candidate. This also alows developers to build with the newest tools and technologies.
3) Name spaces (example code needed)
  * C# uses namespaces heavily in two different ways. 
    * The .NET framework uses namespaces to organize its classes.
    * The traditional, declaring your own namespaces to control the scope of the class (method and variables).
  * In c# we use the 'using' keyword which helps save the developer time that would be wasted on specifying the full name every time a method inside the class is to be called. For example " using Namespace; "
  * In many cases using an 'alias' for a namespace is useful. If you have a namespace that has nested namespaces, it would be good practice to use an 'alias'. for example " using alias = Project.Service.Nested; "
4) Types
    * bool, char, byte sbyte, uint, long, ulong, object, ushort. string. With Object and String as the only non-simple types.
    * Are both reference and value types supported?
    * In C# both reference and value types are supported. C# provides two types - a class and a struct. Structs can have similar members as classes, which can be fields, methods, perperties, or operators.
    * Reference types are created on the heap. The following types are Reference types: dynamic, object, string. In order to declare a reference type you must use one of the following keywords: class, interface, delegate.
    * Value types are created on the stack. The following types are value types: structs and enumerations.
      * Structs fall into the following categories: Numeric types (integra, floating-point, and decimal types), bool, and user defined structs.
    * It is possible to create a new value type in C#. C# does not however, have a type system that supports checking integer ranges at compile time, so you would not be able to change the range of your new type with a range from 1-100 when the limit is set to 0-255.
5) Classes
  ```c#
 public class myClass
{
    //Fields, properties, methods and events go here...
}
 ```
  * A class in C# is essentially a data structure that encapsulates a set of data and behaviors that belong together as a logical unit, and is used similarly to java, as a bluepring used to create instances or objects at run time. To define a class, you must define the access level, followed by the 'class' keyword and the name of your class. What follows are nay fields (controls the state) and methods(controls the behavior).
  * Creating new instances 
```c#
class Equation
{
    public int x, y;

    // constructor
    public Equation()
    {
        x = 0;
        y = 0;
    }
}
   ```
  * In C# Constructors are the primary way of creating a new instance as well as initilizing them at run time.
  ```c#
  class myClass
{
    ~myClassDestructor()  // destructor
    {
        // cleanup statements...
    }
}
  ```
  * In C# you can only destruct classes, desructors cannot be defined in structs. Classes may only have one destructor, they cannot be inherited or overloaded, nor can they be called (they are called automaticly). A destructor may not take modifiers or have parameters.
6) Instance reference name in data type (class)
  * In C# we use the 'this' keyword to refer to the current instance of the class.
7) Properties
  * A property is just a field, usually with public visiblity, with a mechanism for accessing and writing data to a private variable (get, set).
  * Accessors in C# - If a property has both a 'get' and 'set' accessor, both must be auto-implemented, which is defined by using the 'get' and 'set' keywords without any implementation of your own.
  * A Backing variable is: A field that is used by properties when you want to modify or use that private field data.Backing variables in c# is recomended in most senarios when you are not using automatic properties.
  * Computed properties
```c#
private int age;
public int Age
{
    get
    {
        return age;
    }
    set
    {
        age = value;
    }
}
```
  * C# is absolutely able to use calculated values. When returning or changing a value in a getter or setter, you can either return the value stored in memory or use 'compute' the value from other values in memory or completely customize it. Java and C# act very similarly when it comes to computed properties
8) Interfaces / protocols
  * In C# an interface contains definitions for a group of related functionalities that either a class or a struct can implement. An interface in C# is used similarly to Java.
  * Abilities - Interfaces in C# can contain methods, properties, events, indexers, or any combination of these member types. An interface cannot however contain constants, fields, operators, instance constructors, destructors, or types. Instances can implement other interfaces.
  * Interfaces are used in many cases to create multiple inheritance, as well as allowing inherited-class objects to be used in place of base-class objects, and allow inherited-class objects to make use of base-class behaviors.
9) Inheritance/extension
  * Inheritance is a core OOP characteristic, and is used pretty similarly across languages. Inheritance in C# can be defined as the process where one class aquires the properties of another class. We use the "extends" keyword in order to inherit from another class for example "class myClass extends hisClass". A subclass inherits the properties of its super class.
10) Reflection 
  * Reflection in C# is simply the analysis of code by code in the same system at runtime. Reflection in most statically typed languages is very similar. In reflection you can access and manipulate classes, fields, methods, and constructors. Below you can see a very simple example of reflection in C# where the type of a field is being accessed and analysed:
 ```c#
// Using GetType to get the type info:  
int x = 15;  
System.Type type = x.GetType();  
System.Console.WriteLine(type);
 ```
11) Memory Management
  * C# uses automatic memory management similarly to Java, both employing the technique of *garbage collection*. The Garbage Collector implements specific policies to control the life cycle of data. When objects are created, they are marked as live by default. If an object can't be accessed by downstream code, it is no longer considered in use and is marked as eligible for destruction. After this happens, the object's *destructor* will run and destroy the object itself. This still leaves traces of the objects memory footprint, and is marked for collection. In the last phase of memory management, the garbage collector runs through the memory and removes data marked for collection. 
12) Comparisons of References and Values
  * In C# when two strings are compared, a result is produced that says one string is greater than, less than, or equal. To perform the comparison *==* or *.Equals(object)* can be used. The result of using *==* is determined based on the compile-time types of the objects being compared. *.Equals(object)* is polymorphic and as such can be overridden. The implementation of *.Equals(object)* will depend on the execution-time type of the target object. Another thing to note is that if comparing two things that are *null*, *==* will not cause errors while *.Equals(object)* will. For ordinary data types *==* can be used.

13) Null/Nil References
  * C# uses the *null* literal to represent a reference which does not exist. Null is the default type for reference-type variables like objects, primitive and other ordinary value types cannot be null. C# does support *Nullable Types*, which are types that support the normal range of valid values plus a *null*.

14) Errors and Exception Handling
  * Similarly to Java, C# allows Error and Exception handling through the use of *try-catch* blocks. These allow potential exception-throwing operations inside the try block to perform in an environment that expects a potential failure. If an exception is thrown, the catch block (if given the correct Exception type) will perform whatever operations it contains. Additionally, a *finally* block can be chained to the *try-catch* to ensure chosen instructions are executed before exiting. A simple example of this in practice can be seen below:
  
  ```c#
  try{
       result = num1 / num2;
     }catch (DivideByZeroException e){
       Console.WriteLine("Exception caught: {0}", e);
     }finally{
       cleanUp(); 
     }
  ```
  * To define your own Exceptions, a new Class can be created by extending the original Exception class or others already doing so.
  ```c#
   public class TempIsZeroException: Exception{
     public TempIsZeroException(string message): base(message){}
   }
  ```

15) Lambda Expressions, Closures, Functions as Types
  * Lambda Expressions in C# are anonymous functions that can be used to create delegates or expression tree types. They allow writing of local functions that can be passed as arguments or returned as the value of function calls. Delegates are the equivalent of *Function Types*
  
  **Assigning an expression to a delegate type**
  ```c#
  delegate int del(int i);  
  static void Main(string[] args){  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
  }  
  ```
  
  **Creating an Expression Tree Type**
  ```c#
  using System.Linq.Expressions;  
  
  namespace ConsoleApplication1{ 
    class Program{ 
        static void Main(string[] args){  
            Expression<del> myET = x => x * x;  
        }  
    }  
  } 
  ```

  * A *closure* in C# takes the form of an in-line delegate/anonymous method. A closure is attached to its parent method meaning that variables defined in parent's method body can be referenced from within the anonymous method. See below example:
  
  ```c#
  public Person FindById(int id){
    return this.Find(delegate(Person p){
        return (p.Id == id);
    });
  }
  ```
  
16) Listeners and Event Handlers
  * C# supports both Event Handling and Listening. To create an Event Handler that performs everything specified by the developer, the *EventHandler Delegate* is used. It takes as input the type of event it will be handling, and being a Delegate it essentially points to the method that will execute the appropriate instructions. Event Listening is done through the *EventListener* Class, which makes the subscription to events possible. The listener represents the target for all events generated by event source.

17) Singleton
   * A singleton can be implemented many ways in C#.  Some ways allow the singleton to be thread-safe and lazily instantiated, others do not. All implementations do share similarities though. All have a single constructor which is private and parameterless. The class is also sealed, which means it can not be subclassed or inherited from. Additionally, the class implementation has a static variable that holds a reference to the singleton instance if it has been instantiated. Lastly, a public static method must exist to get a reference to the instance of the Singleton. Singletons can be made thread-safe using locks to ensure threads don't interfere with another, and full lazy instantiation can be achieved by using a nested class. The following code example should help to demonstrate this:
   
   ```c#
   public sealed class Singleton{
   
    private Singleton(){}
    public static Singleton Instance { get { return Nested.instance; } }
        
    private class Nested{
        // Explicit static constructor to tell C# compiler
        // not to mark type as beforefieldinit
        static Nested(){}

        internal static readonly Singleton instance = new Singleton();
    }
   }
   ```

18) Procedural Programming
  * Both C# and Java support procedural programming, as it is up to the developer to implement the OOP features the language brings. Procedural programming consists of sequences of imperative statements, assignments, tests, loops and invocations of sub procedures. This type of programming is not encouraged in OOP due to the challenges and difficulties it brings with maintenance of the code-base in large-scale projects.

19) Functional Programming
  * C# can be considered a functional programming language as it does provide some features unique to higher order programming. As of C# 2.0, developers are allowed to pass and return functions as values for higher order functions, and includes limited support for anonymous delegates. Anonymous delegates allow the programmer to encapsulate a method reference in a *delegate* object. Delegate's do not care about the class of the object it references, only the method's argument types and return types must match. In C# 3.0 and 3.5 also came improved support for anonymous functions as true closures.

20) MultiThreading
    * C# supports parallel execution of applications through multithreading, like many other languages. This functionality is dependent on the *System.Threading.Thread* class, which enables creation and access of threads adjacent to the main thread. This system *Thread* class has a *CurrentThread* property that is used to access threads. Similar to other languages, there are four distinct states threads can be in. Unstarted, Ready, Not Runnable, and Dead. When a thread has been created, but not yet started execution it lies in the Unstarted state. Once the *start()* method of the Thread is called, it enters the *Ready* state. This signifies the thread is waiting to be scheduled on the CPU. If thread is interrupted by the *sleep()* method, the *wait()* method, or I/O operations, it is placed in the *Not Runnable* state until it can be scheduled on the CPU again. Lastly, when a thread completes execution or is aborted, it is placed in the *Dead* state. C# also supports thread priority levels, but it's important not to set priorities of user threads too high. If this is done it is possible to lock up the host platform due to placing user tasks above system ones.
