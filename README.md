# Android-Java-Interview-Quesions-Answer


**1. What are the access modifiers in JAVA ?**

    There are four access modifiers in Java language (from strictest to the most lenient):
    
    1.private = 
    variables, methods, constructors or inner classes are only visible to its' containing class and its' methods. This modifier is most 
    commonly used, for example, to allow variable access only through getters and setters or to hide underlying implementation of classes 
    that should not be used by user and therefore maintain encapsulation. Singleton constructor is also marked private to avoid unwanted 
    instantiation from outside.
    
    2.Default =
    (no keyword is used) this modifier can be applied to classes, variables, constructors and methods and allows access from classes 
    and methods inside the same package.

    3.protected = 
    can be used on variables, methods and constructors therefore allowing access only to subclasses and classes that are inside the same 
    package as protected members' class.
    
    4.public = 
    modifier is widely-used on classes, variables, constructors and methods to grant access from any class and method anywhere. 
    It should not be used everywhere as it implies that data marked with public is not sensitive and can not be used to harm the program.
    
**2. Explain Generics in Java ?**

    Generics were included in Java language to provide stronger type checks, by allowing the programmer to define, which classes 
    can be used with other classes

    In a nutshell, generics enable types (classes and interfaces) to be parameters when defining classes, interfaces and methods. 
    Much like the more familiar formal parameters used in method declarations, type parameters provide a way for you to re-use the 
    same code with different inputs. The difference is that the inputs to formal parameters are values, while the inputs to type 
    parameters are types.

    This means that, for example, you can define:

    List<Integer> list = new ArrayList<>();
    And let the compiler take care of noticing, if you put some object, of type other than Integer into this list and warn you.

    It should be noted that standard class hierarchy does not apply to generic types. It means that Integer in List<Integer> 
    is not inherited from <Number> - it is actually inherited directly from <Object>. You can still put some constraints on what 
    classes can be passed as a parameter into a generic by using wildcards like <?>, <? extends MyCustomClass> or <? super Number>.

    While generics are very useful, late inclusion into Java language has put some restraints on their implementation - 
    backward compatibility required them to remain just "syntactic sugar" - they are erased (type erasure) during compile-time and replaced with object class.
    
**3. What is Java PriorityQueue? - 

    In Priority Queue, each element is having some priority and all the elements are present in a queue. The operations are performed based on the priority.
    
**4. Object scopes ?**

    public , protected , default (no modifier) , private

    Modifier	             Package	 Subclass	  World
    Public	               Yes	     Yes	      Yes
    protected	             Yes	     Yes	      No
    Default (no modifier)	 Yes	     No 	      No
    private	               No	       No	        No
    
**5. Override private methods, possible ?**

    No, a private method cannot be overridden since it is not visible from any other class.
    
**6. What is the difference between initialization and instantiation ?**

    Instantiation is when memory is allocated for an object. This is what the new keyword is doing. A reference to the object that was created 
    is returned from the new keyword.

    Initialization is when values are put into the memory that was allocated. This is what the Constructor of a class does when 
    using the new keyword. A variable must also be initialized by having the reference to some object in memory passed to it.
    
**7. What does the keyword synchronized mean ?**

    A synchronized block in Java is synchronized on some object. All synchronized blocks synchronized on the same object can only 
    have one thread executing inside them at a time. All other threads attempting to enter the synchronized block are blocked until 
    the thread inside the synchronized block exits the block.
    
**8. what is the difference between throw and throws ?**

    Keyword throw is used to explicitly throw as an exception in the body of function, while throws is utilized to handle checked exceptions 
    for re-intimating the compiler that exceptions are being handled. The throws need to be used in the function’s signature and also 
    while invoking the method that raises checked exceptions.
    
**9. What is the use of the finalize method?

    finalize() method is a protected and non-static method of java.lang.Object class. This method will be available in all objects you create in java. 
    This method is used to perform some final operations or clean up operations on an object before it is removed from the memory. 
    you can override the finalize() method to keep those operations you want to perform before an object is destroyed. Here is the general form of finalize() method.

    protected void finalize() throws Throwable {
	   //Keep some resource closing operations here
    }
    
**10. Why the main () method in Java is always static ?**

    Java main() method is always static, so that compiler can call it without the creation of an object or before the creation of an object of the class.

    In any Java program, the main() method is the starting point from where compiler starts program execution. 
    So, the compiler needs to call the main() method.
    If the main() is allowed to be non-static, then while calling the main() method JVM has to instantiate its class.
    While instantiating it has to call the constructor of that class, There will be ambiguity if the constructor of that class takes an argument.
    Static method of a class can be called by using the class name only without creating an object of a class.
    The main() method in Java must be declared public, static and void. If any of these are missing, the Java program will compile but a 
    runtime error will be thrown.
    
**11. How to prevent a class to be extended ?**

    simply use keyword final in definition of class or methods. 
    
**12. why access to the non-static variable is not allowed from static method in Java?

    because non-static variable are associated with a specific instance of an object while static is not associated with any instance.
    
**13. What is the difference between == and .equal ?**

    The equals() method compares two strings, character by character, to determine equality.
    The == operator checks to see whether two object references refer to the same instance of an object
    
**14. Reflection in Java ?**

    Reflection is an API that is used to examine or modify the behavior of methods, classes, and interfaces at runtime. 
    The required classes for reflection are provided under java.lang.reflect package which is essential in order to understand reflection.
    
**15. Java Threads ?**

    Threads allows a program to operate more efficiently by doing multiple things at the same time.
    Threads can be used to perform complicated tasks in the background without interrupting the main program.
    There are two ways to create a thread.

     1. It can be created by extending the Thread class and overriding its run() method:
     2. Another way to create a thread is to implement the Runnable interface:
    
**16. Multithreading in Java ?**

    Java is a multi-threaded programming language which means we can develop multi-threaded program using Java. 
    A multi-threaded program contains two or more parts that can run concurrently and each part can handle a different task at the 
    same time making optimal use of the available resources specially when your computer has multiple CPUs.

    By definition, multitasking is when multiple processes share common processing resources such as a CPU. Multi-threading extends the idea of 
    multitasking into applications where you can subdivide specific operations within a single application into individual threads. 
    Each of the threads can run in parallel. The OS divides processing time not only among different applications, but also among each thread within an application.

    Multi-threading enables you to write in a way where multiple activities can proceed concurrently in the same program.
    
**17. Java Enums ?**

    An enum is a special "class" that represents a group of constants (unchangeable variables, like final variables).
    To create an enum, use the enum keyword (instead of class or interface), and separate the constants with a comma. 
    Note that they should be in uppercase letters:
	
    enum Level {
	LOW,
	MEDIUM,
	HIGH
    }
    
**18. What is thread-safe mean? How we can make our code thread-safe ?**

    Thread safety in java is the process to make our program safe to use in multithreaded environment, there are different ways through which 
    we can make our program thread safe.

    Synchronization
    Use of Atomic Wrapper, For example AtomicInteger.
    Use of locks from java.util.concurrent.locks package.
    Using thread safe collection classes
    Using volatile keyword.
    Note that if two threads are both reading and writing to a shared variable, then using the volatile keyword for that is not enough. 
    You need to use a synchronized in that case to guarantee that the reading and writing of the variable is atomic. Reading or writing a volatile 
    variable does not block threads reading or writing. For this to happen you must use the synchronized keyword around critical sections.
    
**19.Mutable and Immutable in Java ?**
	
    The mutable objects are objects whose value can be changed after initialization. We can change the object's values, 
    such as field and states, after the object is created. For example, Java.util.Date, StringBuilder, StringBuffer, etc.

    When we made a change in existing mutable objects, no new object will be created; instead, it will alter the value of the existing object. 
    These object's classes provide methods to make changes in it.
	
    The immutable objects are objects whose value can not be changed after initialization. We can not change anything once the object is created. 
    For example, primitive objects such as int, long, float, double, all legacy classes, Wrapper class, String class, etc.
    
**20. What is the volatile modifier ?**

    In multi-threading apps where the threads operate on non-volatile variables, each thread may copy variables from main memory 
    into a CPU cache, for performance reason. If your app run on more than one thread, each thread may copy the variable and cache it. 
    So This keyword is used to mark a variable as "being stored in main memory". Note that reading from and writing to main memory is 
    more expensive than accessing the CPU cache. Thus, you should only use volatile variables when you really need to enforce visibility of variables.
    
**21. What is transient modifier? What does it come for ?**

    transient is a variables modifier used in serialization. At the time of serialization, if we don’t want to save value of a particular 
    variable in a file, then we use transient keyword. When JVM comes across transient keyword, it ignores original value of the variable 
    and save default value of that variable data type.
    
    
    
