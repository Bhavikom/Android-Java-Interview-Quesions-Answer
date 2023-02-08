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

    A process of converting one data type to another is known as Typecasting.
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

**37. What is the difference between fail-fast and fail-safe iterators in Java ?**

    Fail-safe iterator will not throw any exception even if the collection is modified while iteration over it. 
    But in Fail-safe iterator, it throws a ConcurrentModificationException when you try to modify the collection while using it.
    
**38. What is Java Anonymous Class ?**

    In Java, a class can contain another class known as nested class. It's possible to create a nested class without giving any name.

    A nested class that doesn't have any name is known as an anonymous class.

    An anonymous class must be defined inside another class. Hence, it is also known as an anonymous inner class. Its syntax is:

    class outerClass {
        // defining anonymous class
        object1 = new Type(parameterList) {
        // body of the anonymous class
        };
    }
    Anonymous classes usually extend subclasses or implement interfaces.
    Here, Type can be
    
    a superclass that an anonymous class extends
    an interface that an anonymous class implements
    The above code creates an object, object1, of an anonymous class at runtime.

    Note: Anonymous classes are defined inside an expression. So, the semicolon is used at the end of anonymous classes to indicate the end of the expression.
    
    Example 1: Anonymous Class Extending a Class
    class Polygon {
        public void display() {
           System.out.println("Inside the Polygon class");
        }
    }
    class AnonymousDemo {
        public void createClass() {
        // creation of anonymous class extending class Polygon
        Polygon p1 = new Polygon() {
           public void display() {
              System.out.println("Inside an anonymous class.");
          }
        };
        p1.display();
       }
   }
   class Main {
       public static void main(String[] args) {
          AnonymousDemo an = new AnonymousDemo();
          an.createClass();
       }
   }

   Output : Inside an anonymous class.
   
   Example 2: Anonymous Class Implementing an Interface

   interface Polygon {
      public void display();
   }
      class AnonymousDemo {
        public void createClass() {
        // anonymous class implementing interface
        Polygon p1 = new Polygon() {
          public void display() {
            System.out.println("Inside an anonymous class.");
          }
        };
        p1.display();
      }
   }
   class Main {
      public static void main(String[] args) {
         AnonymousDemo an = new AnonymousDemo();
         an.createClass();
      }
   }

   Output :-
   Inside an anonymous class.
   In the above example, we have created an anonymous class that implements the Polygon interface.
   
**39. Advantages of Anonymous Classes ?**

   In anonymous classes, objects are created whenever they are required. That is, objects are created to perform some specific tasks. For example,
   Object = new Example() {
      public void display() {
          System.out.println("Anonymous class overrides the method display().");
      }
   };
   Here, an object of the anonymous class is created dynamically when we need to override the display() method.
   Anonymous classes also help us to make our code concise.
   
**40. Explain Memory Leak in Java ?**

   Java provides out-of-box memory management. When we create an object using the new keyword, the JVM automatically allocates memory for that object. 
   If the object is no longer is used by the application, the garbage collector automatically removes that object and free up space for other applications. 
   Therefore, the programmer need not to manage memory manually like other procedural programming languages (C, and C++). Nevertheless, 
   there is a chance of memory leak in a Java application. In this section, we will understand what is a memory leak in Java, its causes, 
   detect and fixing of memory leaks.

   *What is memory leak in Java?
   In Java, the memory leak is a situation when the garbage collector does not recognize the unused objects and they remain in the memory 
   indefinitely that reduces the amount of memory allocated to the application. Because the unused objects still being referenced that may 
   lead to OutOfMemoryError. It also affects the reliability of the application. 
   
   *Causes of Memory Leaks
   
    There are the following causes of memory leaks in Java:

    1.Using Unwanted Object Reference: These are the object references that are no longer needed. The garbage collector is failed to 
    reclaim the memory because another object still refers to that unwanted object.
    
    2.Using Long-live Static Objects: Using static objects also leads to a memory leak. Because they live in the memory till the application's life span.
    
    3.Failure to Clean-up Native System Resources: Native system resources allocated by a function external to Java. It is written in C and C++. JNI APIs are used to       embed native libraries in the Java code.
    
    4.Bugs in the Third-party Libraries: Bugs in AWT and Java Swing packages are another cause of memory leak.
    
    *Preventing Memory Leak
    
    While writing code, remember the following points that prevent the memory leak in Java.

    1.Do not create unnecessary objects.
    2.Avoid String Concatenation.
    3.Use String Builder.
    4.Do not store a massive amount of data in the session.
    5.Time out the session when no longer used.
    6.Do not use the System.gc() method.
    7.Avoid the use of static objects. Because they live for the entire life of the application, by default. So, it is better to set the reference to null, explicitly.
    8.Always close the ResultSet, Statements, and Connection objects in the finally block.
    
**41. What are the differences between a SparseArray and Hashmap ?**

    Sparse arrays can be used to replace hash maps when the key is an Integer or a Long (HashMap <Integer, V>).
    is made to be memory efficient than using the regular HashMap
    It is generally slower than a traditional HashMap
    
**42. What are the differences between a LinkedList vs ArrayList ?**

    two different implementations of the List interface
    LinkedList implements it with a doubly-linked list.
    ArrayList implements it with a dynamically re-sizing array.
    LinkedList is better for working with stacks mostly, or when working with buffers.
    ArrayList is best for working with indexes.
    
**43. What is the difference between HashSet, HashMap and Hashtable? How do they behave in a multi-threaded environment?

    1. Hashtable
       Hashtable is basically a data structure to retain values of key-value pair.

       It does not allow null for both key and value. It will throw NullPointerException.
       Hashtable does not maintain insertion order. The order is defined by the Hash function. So only use this if you do not need data in order.
       It is synchronized. It is slow. Only one thread can access in one time.
       HashTable rea thread safe.
       HashTable uses Enumerator to iterate through elements.
       Hashtable<Integer,String>; myTable = new Hashtable<Integer,String>();

       myTable.put(1, "John");
       myTable.put(2, "Cena");
       myTable.put(3, null); /* NullPointerEcxeption at runtime*/

       System.out.println(myTable.get(1));
       System.out.println(myTable.get(2));
       System.out.println(myTable.get(3));

    2.HashMap

       Like Hashtable it also accepts key value pair.

       It allows null for both key and value.
       HashMap does not maintain insertion order. The order is defined by the Hash function.
       It is not synchronized. It will have better performance.
       HashMap are not thread safe, but you can use Collections.synchronizedMap(new HashMap<K,V>())
       HashMap<Integer,String> myMap = new HashMap<Integer,String>();

       myMap.put(1, "First");
       myMap.put(2,"Second");
       myMap.put(3, null);
       
    3.HashSet
    
       HashSet does not allow duplicate values.
       It provides add method rather put method.
       You also use its contain method to check whether the object is already available in HashSet. HashSet can be used where you want 
       to maintain a unique list.

       HashSet<String> mySet = new HashSet<String>();
       mySet.add ("First");
       mySet.add ("Second");
       mySet.add ("Third");
       if(mySet.contains("First")){
          System.out.println("The Set already contains First");
       }
     
**44. What is a Deadlock In java ?**

    Deadlock describes a situation where two or more threads are blocked forever, waiting for each other.
    
**45. How we can avoid Deadlocks ?**

    Breaking circular wait condition: In order to do that, you can make arrangements in the code to impose the ordering on acquisition and release of locks.
    
    Avoid Nested Locks: This is the most common reason for deadlocks, avoid locking another resource if you already hold one. 
    It’s almost impossible to get a deadlock     situation if you are working with only one object lock.
    
    Lock Only What is Required: You should acquire lock only on the resources you have to work on, if we are only interested in one of its fields, 
    then we should lock only that specific field, not complete object.
    
    Avoid waiting indefinitely: You can get a deadlock if two threads are waiting for each other to finish indefinitely using thread join. 
    If your thread has to wait for another thread to finish, it’s always best to use join with the maximum time you want to wait for the thread to finish.

**46. What is the difference between a process and a thread in Java/Android ?**

    1.A program in execution is often referred to as Process. A thread is a part of the process.
    
    2.A process consists of multiple threads. A thread is the smallest part of the process that can execute concurrently with other threads of the process.
    
    3.A process is sometimes referred to as “Task”. A thread is often referred to as a “Lightweight” process.
    
    4.A process has its own address space. A thread uses the process’s address space and shares it with the other threads of that process.
    
    5.A thread can communicate with other threads (of the same process) directly by using methods like wait(), notify(), notifyAll(). 
    
    6.A process can communicate with another process by using inter-process communication (IPC/AIDL).
    
    7.New threads are easily created. However, the creation of new processes requires duplication of the parent process.
    
    8.Threads have control over the other threads of the same process. A process does not have control over the sibling process, 
    it has control over its child processes only.
    
**47. How do you manipulate strings in Java without creating String garbage ?**

    Using StringBuilder and StringBuffer/StringBuilder
    
**48. In Java, does the finally block gets executed if we insert a return statement inside the try block of a try-catch-finally ?

    Yes!
    
**49. Why are Array and ArrayList different? When would you use each ?**

    Resizable: Array is static in size that is fixed length data structure, One can not change the length after creating the Array object. 
    ArrayList is dynamic in size.
    
    Multi-dimensional: Array can be multi dimensional , while ArrayList is always single dimensional.
    
    Primitives: ArrayList can not contains primitive data types (like int , float , double) it can only contains Object while Array can 
    contain both primitive data types as well as objects.
    
**50. What is a ThreadPool? Is it better than using several "simple" Threads ?**

    ThreadPool: represents a group of worker threads that are waiting for the job and reuse many times.
    Using ThreadPool minimizes the overhead due to thread creation. Thread objects use a significant amount of memory, 
    and in a large-scale application, allocating and deallocating many thread objects creates a significant memory management overhead.
    
**51. What are transient and volatile modifiers ?**

    transient: modifier tells the Java object serialization subsystem to exclude the field when serializing an instance of the class
    
    volatile: modifier tells the JVM that writes to the field should always be synchronously flushed to memory, and that reads of the field 
    should always read from memory.
    
**52. What are the states of Thread in Java ?**

    New, Runnable, Blocked, Waiting, TimedWaiting, Terminated.
    
**53. How to make object thread safe without synchronisation ?**

    Make it immutable.
    
**54. Whether static method can use nonstatic members ?**
   
    NO
    
**55. Do objects get passed by reference or value in Java ?**

    In Java all primitives and objects are passed by value, meaning that their copy will be manipulated in the receiving method. 
    But there is a caveat - when you pass an object reference into a method, a copy of this reference is made, so it still points 
    to the same object! This means, that any changes that you make inside this object are retained, when the method exits.
 
**56. Java Lambda Expressions ?**

    Lambda Expressions were added in Java 8.

    A lambda expression is a short block of code which takes in parameters and returns a value. 
    Lambda expressions are similar to methods, but they do not need a name and they can be implemented right in the body of a method.
    
    Example
    Use a lambda expression in the ArrayList's forEach() method to print every item in the list:

    import java.util.ArrayList;

    public class Main {
  	public static void main(String[] args) {
    	ArrayList<Integer> numbers = new ArrayList<Integer>();
    	numbers.add(5);
    	numbers.add(9);
    	numbers.add(8);
    	numbers.add(1);
    	numbers.forEach( (n) -> { System.out.println(n); } );
  	}
    }
    
**57. What is upcasting and downlcasting in Java ?**

    Upcasting and Downcasting is the type of object typecasting. In Java, the object can also be typecasted like the datatypes. 
    Parent and Child objects are two types of objects. So, there are two types of typecasting possible for an object, i.e., Parent to 
    Child and Child to Parent or can say Upcasting and Downcasting.

    In Java, the object can also be typecasted like the datatypes. Parent and Child objects are two types of objects. So, there are 
    two types of typecasting possible for an object, i.e., Parent to Child and Child to Parent or can say Upcasting and Downcasting.

    Typecasting is used to ensure whether variables are correctly processed by a function or not. In Upcasting and Downcasting, we 
    typecast a child object to a parent object and a parent object to a child object simultaneously. We can perform Upcasting implicitly 
    or explicitly, but downcasting cannot be implicitly possible
    
   *1.Upcasting : - 
   
   Upcasting is a type of object typecasting in which a child object is typecasted to a parent class object. By using the Upcasting, 
   we can easily access the variables and methods of the parent class to the child class. Here, we don't access all the variables 
   and the method. We access only some specified variables and methods of the child class. Upcasting is also known as Generalization and Widening.

   UpcastingExample.java

   class  Parent{  
       void PrintData() {  
          System.out.println("method of parent class");  
       }  
   }  
   class Child extends Parent {  
       void PrintData() {  
          System.out.println("method of child class");  
       }  
   }  
   class UpcastingExample{  
       public static void main(String args[]) {  
           Parent obj1 = (Parent) new Child();  
           Parent obj2 = (Parent) new Child();   
           obj1.PrintData();  
           obj2.PrintData();  
       }  
   }  
   
   *2.Downcasting : - 
   
   Upcasting is another type of object typecasting. In Upcasting, we assign a parent class reference object to the child class. 
   In Java, we cannot assign a parent class reference object to the child class, but if we perform downcasting, we will not get 
   any compile-time error. However, when we run it, it throws the "ClassCastException". Now the point is if downcasting is not 
   possible in Java, then why is it allowed by the compiler? In Java, some scenarios allow us to perform downcasting. Here, the 
   subclass object is referred by the parent class.

   Below is an example of downcasting in which both the valid and the invalid scenarios are explained:

   DowncastingExample.java

   	//Parent class  
   	class Parent {   
       		String name;   
       		// A method which prints the data of the parent class   
       		void showMessage()   
       		{   
             		System.out.println("Parent method is called");   
       		}   
  	}   
  	// Child class   
  	class Child extends Parent {   
      		int age;   
      		// Performing overriding  
    		@Override  
    		void showMessage()   
    		{   
        		System.out.println("Child method is called");   
    		}   
  	}    
	public class Downcasting{  
   
    		public static void main(String[] args)   
    		{   
        		Parent p = new Child();  
        		p.name = "Shubham";  
          
		        // Performing Downcasting Implicitly   
        		//Child c = new Parent(); // it gives compile-time error   
          
        		// Performing Downcasting Explicitly   
        		Child c = (Child)p;   
    
        		c.age = 18;   
        		System.out.println(c.name);   
        		System.out.println(c.age);   
        		c.showMessage();   
    		}   
	}  
	
	
	* Why we need Upcasting and Downcasting?
	
	In Java, we rarely use Upcasting. We use it when we need to develop a code that deals with only the parent class. 
	Downcasting is used when we need to develop a code that accesses behaviors of the child class.
	![image](https://user-images.githubusercontent.com/35212651/217440525-ed8ebacc-22cc-4115-871f-1f60941579ad.png)


 

    
    
    
