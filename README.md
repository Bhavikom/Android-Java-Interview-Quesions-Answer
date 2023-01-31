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
    
![image](https://user-images.githubusercontent.com/35212651/215474184-86540b0a-c658-4b49-8366-13f13b579af7.png)

    
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
    
**9. What is the use of the finalize method ?**

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
    
**12. why access to the non-static variable is not allowed from static method in Java ?**

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
    
**22. Data Types in Java(Primitve and Non-Primitive(Reference type)) ?**

    1. Primitive Data Types: 
    A primitive data type is pre-defined by the programming language. The size and type of variable values are specified, and it has no additional methods.

    Data types in Java are classified into 4 aspects as int, float, character and boolean. But, in general, there are 8 data types. They are as follows:

    boolean data type
    byte data type
    char data type
    short data type
    int data type
    long data type
    float data type
    double data type
    
    2.Non-Primitive Data Types: 
    
    These data types are not actually defined by the programming language but are created by the programmer. 
    They are also called “reference variables” or “object references” since they reference a memory location which stores the data.
    
    Non-Primitive data types refer to objects and hence they are called reference types. 
    Examples of non-primitive types include Strings, Arrays, Classes, Interface, etc.
    
**23. Difference between primitive and non-primitive data types ?**

    1. Primitive types are predefined in Java. Non-primitive types are created by the programmer and is not defined by Java.
    2. Non Primitive types can be used to call methods to perform certain operations, while primitive types cannot.
    3. A primitive type always has a value, whereas non-primitive types can be null.
    4. A primitive type starts with a lowercase letter, while non-primitive types start with an uppercase letter.
    5. The size of a primitive type depends on the data type, while non-primitive types have all the same size.
    
**24. What is the difference between an Integer and int ?**

    int is a primitive data type (with boolean, byte, char, short, long, float and double), while Integer (with Boolean, Byte, Character, 
    Short,Long, Float and Double) is a wrapper class that encapsulates primitive data type, while providing useful methods to perform different tasks with it.
    
**25. What does it means to say that a String is immutable ?**

    It means that once created, String object's char[] (its' containing value) is declared final and, therefore, it can not be changed during runtime.
    
**26. How is String class implemented? Why was it made immutable?

    There is no primitive variant of String class in Java language - all strings are just wrappers around underlying array of characters, 
    which is declared final. This means that, once a String object is instantiated, it cannot be changed through normal tools of the 
    language (Reflection still can mess things up horribly, because in Java no object is truly immutable). This is why String variables
    in classes are the first candidates to be used, when you want to override hashCode() and equals() of your class - you can be sure, 
    that all their required contracts will be satisfied.

    Note: The String class is immutable, so that once it is created a String object cannot be changed. The String class has a number of methods, 
    some of which will be discussed below, that appear to modify strings. Since strings are immutable, what these methods really do is 
    create and return a new string that contains the result of the operation. (Official Java Documentation)

    This class is also unique in a sense, that, when you create an instance like this:

    String helloWorld = "Hello, World!";
    "Hello, World!" is called a literal and compiler creates a String object with its' value. So

    String capital = "Hello, World!".toUpperCase();
    is a valid statement, that, firstly, will create an object with literal value "Hello, World!" and then will create and return 
    another object with value "HELLO, WORLD!"

    String was made immutable to prevent malicious manipulation of data, when, for example, user login or other sensitive data is being send to a server.
    
**27. What is String.intern()? When and why should it be used ?**

    String.intern() is used to mange memory in Java code. It is used when we have duplicates value in different strings. When you call the String.intern(), 
    then if in the String pool that string is present then the equals() method will return true and it will return that string only.
    
**28. What is Autoboxing and Unboxing ?**

    Autoboxing and Unboxing is the process of automatic wrapping (putting in a box) and unwrapping (getting the value out) of primitive data types, 
    that have "wrapper" classes. So int and Integer can (almost always) be used interchangeably in Java language, meaning a method void 
    giveMeInt(int i) { ... } can take int as well as Integer as a parameter.
    
**29. Typecast in Java ?**

    In Java, you can use casts to polymorph one class into another, compatible one. For example:
    long i = 10l;
    int j = (int) i;
    long k = j;
    Here we see, that, while narrowing (long i -> int j) requires an explicit cast to make sure the programmer realizes, that there may be some data
    or precision loss,     widening (int j -> long k) does not require an explicit cast, because there can be no data loss 
    (long can take larger numbers than int allows).
    
**30. Do objects get passed by reference or value in Java? Elaborate on that. ?**

    In Java all primitives and objects are passed by value, meaning that their copy will be manipulated in the receiving method. 
    But there is a caveat - when you pass an object reference into a method, a copy of this reference is made, so it still points to the same object. 
    This means, that any changes that you make to the insides of this object are retained, when the method exits.
    public class Pointer {
    	int innerField;
    	public Pointer(int a) {
        	this.innerField = a;
    	}
    }
    public class ValueAndReference {
	public static void main(String[] args) {
        	Pointer a = new Pointer(0);
        	int b = 1;
        	print("Before:");
        	print("b = " + b);
        	print("a.innerField = " + a.innerField);
        	exampleMethod(a, b);
        	print("After:");
        	print("b = " + b);
        	print("a.innerField = " + a.innerField);
    	}
    	static void exampleMethod(Pointer a, int b) {
        	a.innerField = 2;
        	b = 10;
    	}
    	static void print(String text) {
        	System.out.println(text);
    	}
    }
    Will output:
     Before:
     b = 1
     a.innerField = 0
     After:
     b = 1        // a new local int variable was created and operated on, so "b" didn't change
     a.innerField = 2 // Pointer a got its' innerField variable changed
                     //  from 0 to 2, because method was operating on
                     //  the same reference to an instance
		     
**31. What the difference between local, instance and class variables ?**

     Local variables exist only in methods that created them, they are stored separately in their respected Thread Stack 
     (for more information, see question about Java Memory Model) and cannot have their reference passed outside of the method scope.
     That also means that they cannot be assigned any access modifier or made static - because they only exist during enclosing method's 
     execution and those modifiers just do not make sense, since no other outside method can get them anyway.
     
     Instance variables are the ones, that are declared in classes and their value can be different from one instance of the class to another, 
     but they always require that class' instance to exist.
     
     Class variables are those, that are marked with static keyword in their class' body. They can only have one value across all 
     instances of that class (changing it in one place will change it in their class and, therefore, in all instances) and can even be 
     retrieved without that class' instance (if their access modifier allows it).
     
**32. What is garbage collector? How does it work ?**

     All objects are allocated on the heap area managed by the JVM. As long as an object is being referenced, the JVM considers it alive. 
     Once an object is no longer referenced and therefore is not reachable by the application code, the garbage collector removes it and 
     reclaims the unused memory.
     
**33. Difference Between Checked and Unchecked Exceptions in Java ?**

     A checked exception is caught at compile time whereas a runtime or unchecked exception is, as it states, at runtime.
     A checked exception must be handled either by re-throwing or with a try catch block, whereas an unchecked isn’t required to be handled.
     A runtime exception is a programming error and is fatal whereas a checked exception is an exception condition within your code’s 
     logic and can be recovered or re-tried from.

**34. What is the hashCode() and equals() used for ?**

     The equals() and hashcode() are the two important methods provided by the Object class for comparing objects. 
     Since the Object class is the parent class for all Java objects, hence all objects inherit the default implementation of these two methods. 
     
     1. Java equals()
     The java equals() is a method of lang.Object class, and it is used to compare two objects.
     To compare two objects that whether they are the same, it compares the values of both the object's attributes.
     By default, two objects will be the same only if stored in the same memory location.
     Syntax:
     public boolean equals(Object obj)  
     
     2. Java hashcode()
     A hashcode is an integer value associated with every object in Java, facilitating the hashing in hash tables.
     To get this hashcode value for an object, we can use the hashcode() method in Java. It is the means hashcode() method that returns 
     the integer hashcode value of the given object.
     Since this method is defined in the Object class, hence it is inherited by user-defined classes also.
     The hashcode() method returns the same hash value when called on two objects, which are equal according to the equals() method. 
     And if the objects are unequal, it usually returns different hash values.
     Syntax:
     public int hashCode() 
     
**35. What are these final, finally and finalize keywords ?**

     1.final is a keyword in the java language. It is used to apply restrictions on class, method and variable. 
     Final class can't be inherited, final method can't be overridden and final variable value can't be changed.
     class FinalExample {
        public static void main(String[] args) {
         final int x=100;
         x=200;//Compile Time Error because x is final
        }
     }
     
     2.finally is a code block and is used to place important code, it will be executed whether exception is handled or not.
     class FinallyExample {
     public static void main(String[] args) {
        try {
            int x=300;
        }catch(Exception e) {
            System.out.println(e.getMessage());            }
        finally {
            System.out.println("finally block is executed");
        }
       }
     }
     
     3.Finalize is a method used to perform clean up processing just before object is garbage collected.
     class FinalizeExample {
        public void finalize() {
           System.out.println("finalize called");
        }
        public static void main(String[] args) {
          FinalizeExample f1=new FinalizeExample();
          FinalizeExample f2=new FinalizeExample();
          f1=null;
          f2=null;
          System.gc();
        }
    }
    
**36. Difference between StringBuffer and StringBuilder ?**

    Java provides three classes to represent a sequence of characters: String, StringBuffer, and StringBuilder. 
    The String class is an immutable class whereas StringBuffer and StringBuilder classes are mutable. 
    There are many differences between StringBuffer and StringBuilder. The StringBuilder class is introduced since JDK 1.5.

    A list of differences between StringBuffer and StringBuilder is given below:

    ![image](https://user-images.githubusercontent.com/35212651/215666751-b3f801df-f61a-4757-988c-048aae4f4dd6.png)

     

 

    
    
    
