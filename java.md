Java Criteria

1) Language purpose/genesis
  * Java was created at Sun Microsystems by a team that wanted to create a language that worked across several consumer devices. The language tried to address the issue of uniformality. The creators of java wanted to have a language that would have as few implemnetation dependencies as possible. "Write once and run anywhere". Java wasn't necessaritly meant to replace any other language but was somewhat derived from c and c++ but in the form of a higher level language.
2) Unique features of the language
  * One of the most unique things about Java is the JVM. A Java Application can run on any operating system that can run a JVM (Java Virtual Machine). This makes Java a language that nearly anyone can compile and run on their machine.
3) Name spaces
  * In java, the platform includes packages that start with java, org.omg., javax, along with other that are defined in Sun's standard extensions. Packages can hold subPackages which holds classes. Packages may also hold classes directly without any subpackages.
  * To specify a class is to be part of a package you must use the 'package' keyword before defining the package.subPackage.subSubPackageWhereTheFileIs;
  * packages are used to to "partition the java namespace and prevent name collisions" or in other words be able to reuse names for classes while the compiler is still able to discern the difference between the two.
4) Types
    * Java supports a multitude of types from Primitive data types: byte, short, int, long, float, double, boolean, and char. Java also has Reference data types, which would be any variable that is created using defined constructors of its class. The refeence variables are used to do just that, reference. The default value of any reference variable is null. In java you also have objects and classes. A class is used as a blueprint of the object with the fields storing the state and the method defining the behavior of the object. You cannot create a new primitive data type, you can  however mock a new object to act as if it was though.
5) Classes
   * Defining
   * A class in java is a blueprint from which individual objects are created. A class is defined by a first defining the access level, then use the 'class' keyword followed by the name of the class. What inside of the class you may have fields and methods.
   * Creating new instances
   * In order to create a new instance of a class you need to call one of the two reflective methods. The first is 'java.lang.reflect.Constructor.newInstance()'. The second way is by calling the following method 'Class.newInstance()'. The former is preferred because of a few things: it can invoke any constructor regardless of the number of paremeters, it always wraps the thrown exception with 'InvocationTargetException', and it may invode private constructors under certain circumstances.
   * In java there are three mechanisms that ensure proper initilization of classes (objects). instance initializers, instance variable initializers, and constructors. We can initilize the default values of these variables. For example:
 ```java   
   class SomeClass
{
   static boolean b;
   static byte by;
   static char c;
   static double d;
   static float f;
   static int i;
   static long l;
   static short s;
   static String st;
}
```
   * Since Java is a garbage collected language we cannot predict when or if an object will be destroyed. The reason is because all Java objects are heap allocated and thus garbage collected.
6) Instance reference name in data type (class)
   * In Java we use the 'this' keyword to refer to the current instance of the class.
7) Properties
  * Accessors in Java - In Java we use getters to 'Access' data and setters to 'mutate' data. Getters return a classes variable/value and a setter sets a classes variable or its value. 
  * Backing variables - Java does not use any backing variables. This is because there is no need to back a varibale when in java, instance variables are private which forces developers to use methods (getters, setters, and others) to restrict access.
  * Computed properties - Using a 'get' or 'set' method in Java can be used to 'get' or 'set' a value stored in memory. Or these methods can be used to 'get' or 'set' a custom value (computed).
```java
  // Stored properties
var firstName: String = "First"
var lastName: String = "Last"

// Computed property
var fullName: String {
   return "\(firstName) \(lastName)"
}

// Getting the property
fullName

// Alternatively, you could use a function
func fullName() -> String {
   return "\(firstName) \(lastName)"
}

// Getting fullName
fullName()
```

8) Interfaces / protocols
  * In Java an interface contains definitions for a group of related functionalities that either a class or a struct can implement. An interface in C# is used similarly to C#.
  * Abilities - Interfaces in Java can contain methods, properties, events, indexers, or any combination of these member types. An interface cannot however contain constants, fields, operators, instance constructors, destructors, or types. interfaces can implement other interfaces.
  * Interfaces are used in many cases to create multiple inheritance, as well as allowing inherited-class objects to be used in place of base-class objects, and allow inherited-class objects to make use of base-class behaviors.
9) Inheritance/extension
  * Inheritance in Java can be defined as the process where one class aquires the properties of another class. We use the "extends" keyword in order to inherit from another class for example "class myClass extends hisClass". A subclass inherits the properties of its super class.
10) Reflection
  * Reflection in Java is simply the analysis of code by code in the same system at runtime. Reflection in most statically types languages is very similar. In reflection you can access and manipulate classes, fields, methods, and constructors.
```java
  public class FieldSpy<T> {
    public boolean[][] b = {{ false, false }, { true, true } };
    public String name  = "Alice";
    public List<Integer> list;
    public T val;

    public static void main(String... args) {
	try {
	    Class<?> c = Class.forName(args[0]);
	    Field f = c.getField(args[1]);
	    //gets the type of f
	    System.out.format("Type: %s%n", f.getType());
	    //gets the generic type of f
	    System.out.format("GenericType: %s%n", f.getGenericType());

        // production code should handle these exceptions more gracefully
	} catch (ClassNotFoundException x) {
	    x.printStackTrace();
	} catch (NoSuchFieldException x) {
	    x.printStackTrace();
	}
    }
}
``` 
11) Memory Management
  * Java objects reside in a space called the *heap*. The size of the heap varies and can increase or decrease in size while the application runs. When the size of the heap goes over a preset max value, *Garbage Collection* takes over. During this garbage collection objects that are no longer used are cleared, making more space for new objects.
  * The heap is sometimes divided into two areas (or generations) called the nursery (or young space) and the old space. The nursery is a part of the heap reserved for allocation of new objects. When the nursery becomes full, garbage is collected by running a special young collection, where all objects that have lived long enough in the nursery are promoted (moved) to the old space, thus freeing up the nursery for more object allocation. When the old space becomes full garbage is collected there, a process called an old collection.
  
12) Comparison of References and Values
  * To compare primitive and ordinary data types in Java, the *==* is preferred. However, if objects are to be compared the *.equals(object)* method should be used if it is provided. When the *==* sign is used on objects in Java, the actual references to the objects are checked for comparison. If the value of the object is to be compared, use *.equals(object)*.

13) Null/Nil References
  * Java uses *null* as the value for an object to signify the object (really a reference pointer) points to nothing. When an reference pointer is set to *null* as it is when instantiated and not given a value, a *NullPointerException*. Primitive variables however are set 0 or the equivalent when they are not initialized with values by default. 

14) Errors and Exception Handling
  * In Java Error and Exception handling can be taken care of using *try-catch* blocks. These allow potential exception-throwing operations inside the *try* block to perform in an environment that expects a potential failure. If an exception is thrown, the *catch* block (if given the correct Exception type) will perform whatever operations it contains. A simple example of this in practice can be seen below:
  
  ```java
  try{
    customerObject = customerDao.findCustomerById(customerId);
  }catch(Exception ex){
    ex.printStackTrace(); //print stack to help debug and find root cause
    return new Customer();
  }
  ```
  * If the developer would like to *throw* Exceptions themselves to signify error, they can do so using the following syntax:
  
  ```java
  if(object.isValid() == false){
    throw new Exception();  //replace "Exception" with the specific Exception class that best suits application
  }
  ```
  * The *try-catch* block can also be chained with a *finally* block to ensure some code is run before a method might exit after an exception is thrown.
  
  ```java
  try{
     }catch(Exception ex){
     }finally{}
  ```

15) Lambda Expressions, Closures, Functions as Types
  * In Java, Lambda expressions let you express instances of single-method classes more compactly. They enable you to treat functionality as method argument (code as data), and functions as types.  The recipient of lambda's does not need to know that a Lambda is involved, instead it accepts an Interface with the appropriate method. The simplest way of setting all this up is by creating a functional interface. An example doing just this can be seen below:
  
  ```java
  public interface TwoArgIntOperator {
    public int op(int a, int b);
  }

  //elsewhere:
  static int method(TwoArgIntOperator operator) {
     return operator.op(5, 10);
  }
  ```
  
  * A closure is a block of code that can be referenced (and passed around) with access to the variables of the enclosing scope. They can be achieved using anonymous inner classes (which require all local variables *final*) or using Lambdas in Java 8+

16) Listeners and Event Handlers
  * Java supports both Listeners and Event handlers. Listeners subscribe to events from a source using the *observer pattern*, and many listeners can be subscribed to a single source. For objects that support it, Listeners can be added using the *addObjectNameListener()* method. Event Handlers are objects that are responsible for handling events (as named). Handlers can be set for events using a method similar to Listeners. 

17) Singleton
  * Singleton in Java can be implemented similarly to how it is done in C#. A private constructor, private static variable of Singleton instance, and public static method that returns instance of Singleton are still required. To ensure that operations on Singleton are threadsafe, the public static getter method can be given the *synchronized* modifer. *Double Checked Locking* can also be used, which is faster due to less working overhead. An example of this can be seen below:
  
  ```java
  public class ThreadSafeSingleton {

    private static ThreadSafeSingleton instance;
    private ThreadSafeSingleton(){}
    
    public static ThreadSafeSingleton getInstanceUsingDoubleLocking(){
        if(instance == null){
            synchronized (ThreadSafeSingleton.class) {
                if(instance == null){
                    instance = new ThreadSafeSingleton();
                }
            }
        }
        return instance;
    }
  }
  ```

18) Procedural Programming
  * Both C# and Java support procedural programming, as it is up to the developer to implement the OOP features the language brings. Procedural programming consists of sequences of imperative statements, assignments, tests, loops and invocations of sub procedures. This type of programming is not encouraged in OOP due to the challenges and difficulties it brings with maintenance of the code-base in large-scale projects.

19) Functional Programming
  * Functional Programming can be achieved in Java using lambda expressions and anonymous functions. Using these, functions can be passed as arguments to other functions, and *function factories* can be created. An example of this can be seen below, as new functions are produced
  
  ```java
  Function<Integer, Function<Integer,Integer>> makeAdder = x -> y -> x + y;
  Function<Integer,Integer> add1 = makeAdder.apply(1);
  Function<Integer,Integer> add2 = makeAdder.apply(2);
  Function<Integer,Integer> add3 = makeAdder.apply(3);
  ```

20) MultiThreading
  * Like C#, Java also has defined states for threads. The *New* state is for threads that have not yet started execution. Once the *start()* method of the thread has been called, it moves to the *Runnable* state. In this state the thread is executing within the JVM. If a thread attempts to access a resource and it is blocked from waiting for that resource lock, it is placed in the *Blocked* state. If a thread is waiting indefinitely for another thread to perform an action, it moves to the *Waiting* state. Threads can be given timed waits, and if they are waiting on another thread for a specified amount of time they move to the *Timed Waiting* state. Lastly is the *Terminated* state, reserved for threads that have exited execution. Threads can be created by extending an existing **Thread** class, or implementing the **Runnable** interface. However the thread is created, it must begin execution using the *start()* method. Java threads can also be given priority to determine which threads should be scheduled before others, but how this is interpreted is up to the host platform and does not guarantee thread execution order.
