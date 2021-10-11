# Android-Interview-Questions


### What are the main 3 Object Oriented Programing (OOP) concepts?

#### Inheritance 

Java inheritance can be defined as the process where one class acquires property (Field and methods) of another. With the use of inheritance the information made manageable in hierarchical order. 
Inheritance is nothing but mechanism which allow you to reuse code. 
The class which inherits the property of other is known as subclass (derived class . child class) and the class whose property is inherited is known as superclass. 

Type of inheritance : 
Single inheritance , Multi level inheritance, hierarchical inheritance , Multiple inheritance, hybrid  is not supported by java. 
What is the reasons that java doesn’t support for multiple inheritance ?
Because of diamond problem, derivate has two base class and these two base class connects to common base class. Why didn’t java resolve this ? to simplify compiler 
 
#### Polymorphism

It is concept which allows to perform single task in many different ways . 
Polymorphism can be defined as object showing different behaviors at different stages of its life cycle Or performing single action in different ways. 

there are two type of polymorphism - 

Compile time polymorphism - Static polymorphism - method overloading is nothing but a feature that allows class to declare two or more method with same name but different parameters. Example - addition of two methods 

RunTimePolymorphism - method overriding 
in object oriented terms- overriding means to override the functionality of existing method. 
its ability to define a behavior that's specific to the subclass type, which means a subclass implement a parent class method based on its requirements. Override means we are overriding method to rewrite method. 
  

#### Abstraction 
Abstraction is a process of hiding the implementation details from the user, only the functionality will be provided to the user. In other words, the user will have the information on what the object does instead of how it does it.
In Java, abstraction is achieved using Abstract classes and interfaces.


#### Encapsulation 
Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.
To achieve encapsulation in Java −
	• Declare the variables of a class as private. 
	• Provide public setter and getter methods to modify and view the variables values. 


### Explain object serialization and how to implement it in Java. 

Serialization is the process of converting an object into a sequence of bytes which can be persisted to a disk Or database Or Can be sent through streams. The reverse process of creating object from sequence of bytes is called deserialization. 
Java objects are serializable if its class or any of its classes implements java.io.serializable Or subinterface java.io.Externalizable interface. 
Examples are ObjectInputStream and ObjectOutputStream 

### What is Serializable?

Serializable is a standard Java interface. It is not a part of the Android SDK. Its simplicity is its beauty. Just by implementing this interface your POJO will be ready to jump from one Activity to another.

The beauty of serializable is that you only need to implement the Serializable interface on a class and its children. It is a marker interface, meaning that there is no method to implement, Java will simply do its best effort to serialize it efficiently.

The problem with this approach is that reflection is used and it is a slow process. This mechanism also tends to create a lot of temporary objects and cause quite a bit of garbage collection.

### What is Parcelable?

Parcelable is another interface. Despite its rival (Serializable in case you forgot), it is a part of the Android SDK. Now, Parcelable was specifically designed in such a way that there is no reflection when using it. That is because we are being really explicit for the serialization process.

### Explain anonymous classes.
Defining class with no identity, that there is no class names are present. Anonymous inner class are mostly used to provide definition for interfaces.

Consider there is an interface

        Interface A {
          Void f();
        }

        Class Test {

          Public static void main(string arg[]) {

            // Anonymous inner class
            A obj = new A {

              //override
              Void f() {
                // logic
              }
        }
          }
        } 

Why do you need this ? 
	We are implementing interface , nothing but defining interface inside method. Anonymous inner class always should be always written inside method. 


### Describe the differences between abstract classes and interfaces.

1. 
- abstract class : 0 or N number of concrete method OR 0 or N number of abstract method
- Interface : 0 or N number of abstract method only 

2. 
- Abstract : There is no default cases for the methods, every access specifier can be define 
- Interface : There is default cases for interface, it is always public abstract methods

3. 
- Abstract : There is no default cases for the variables, every access specifier can be define.
- Interface : There is default cases for interface, it is always public static final variables

4. Abstract : 

        Constructor {} possible. 
        It is possible to write static block {
        }

        { // non static block
        }

5. 
  - Static method
  - Non static method
  - Every element are allowed declare inside abstraction 
  - Interface :  Non constructor, public methods allowed , nothing else

6. No object creation is possible for both of them.
 
	
Strict rules : you can’t make final OR static to abstract method .why ? reasons any specification, nothing but declaration has to implement in child class. It violate override definition.

Why can’t we make static abstract, why it is illegal ?? definition of the static is, one thing in common , Something which is not common then it should not be defined as static . 

Why can’t we make class as private and protect ? 
What is the use of making class as private, there is no communication to outside world , what is protected member -> within the hierarchy is available , protected members can be only accessed within the family member. 
Making protect to class is nothing but you are communicating within your family and you are not interacting with any outside class member , is that possible ???  

### Explain what a Singleton class is and how to create one in Java 

The Singleton design pattern addresses all of these concerns. With the Singleton design pattern you can:

Ensure that only one instance of a class is created Provide a global point of access to the object Allow multiple instances in the future without affecting a singleton class's clients

        public class ClassicSingleton {
           private static ClassicSingleton instance = null;
           protected ClassicSingleton() {
              // Exists only to defeat instantiation.
           }
        public static ClassicSingleton getInstance() {
              if(instance == null) {
                 instance = new ClassicSingleton();
              }
              return instance;
           }
        }

### Why should the equals() and hashCode() methods often be overridden together?

### What is boxing in java ? 
Converting primitive data into object data is known as Boxing. 
        byte(primitive type) -🡪 Byte (Object type)
        byte x = 100;
        Byte.valueOf( x //primitive type);

### How do you properly override the equals() method? For example, what considerations should be taken when checking for equality? 

### Difference between final, finally and finalize?
Final is used to apply restrictions on class, method and variable. Final class can't be inherited, final method can't be overridden and final variable value can't be changed.	
Final is a keyword.	

Finally is used to place important code, it will be executed whether exception is handled or not.
Finally is a block.	

Finalize is used to perform clean up processing just before object is garbage collected.
Finalize is a method.

In Java, does the finally block gets executed if we insert a return statement inside the try block of a try-catch-finally?
That's actually true in any language...finally will always execute before a return statement, no matter where that return is in the method body. If that wasn't the case, the finally block wouldn't have much meaning.

### Explain method overloading & overriding ?
Method overloading is nothing but a feature that allows class to declare two or more method with same name but different parameters. Example - addition of two methods 

Method overriding - in object oriented terms- overriding means to override the functionality of existing method. 
its ability to define a behavior that's specific to the subclass type, which means a subclass implement a parent class method based on its requirements.   

### What is memory leak and how does Java handle it? 

# Data Structures Questions 

### What the the primitive types in Java ?
There are 8 primitive types:
- byte
- short
- int
- long
- char
- float
- double
- Boolean

### What data structures do we have available to us, as programmers?

Java has two categories of data:
Primitive data (e.g., number, character)
Object data (programmer created types)

Primitive data are only single values; they have no special capabilities. There are 8 primitive data types

Candidates should be able to describe, for any of the data structures above
what you use them for (real-life examples)
why you prefer them for those examples
the operations they typically provide (e.g. insert, delete, find)
the big-O performance of those operations (e.g. logarithmic, exponential)
how you traverse them to visit all their elements, and what order they're visited in
at least one typical implementation for the data structure.

### Why do we need collections ? 

Before Collection Framework (or before JDK 1.2) was introduced, the standard methods for grouping Java objects (or collections) were Arrays or Vectors or Hashtables. All of these collections had no common interface.

Accessing elements of these Data Structures was a hassle as each had a different method (and syntax) for accessing its members:

Advantages of Collection Framework:

Consistent API : The API has a basic set of interfaces like Collection, Set, List, or Map. All classes (ArrayList, LinkedList, Vector, etc) that implement these interfaces have some common set of methods.

Reduces programming effort: A programmer doesn’t have to worry about the design of Collection, and he can focus on its best use in his program.

Increases program speed and quality: Increases performance by providing high-performance implementations of useful data structures and algorithms.
Hierarchy of Collection Framework

             Collection                Map
         /     /    \      \            |
        /      /      \     \           |
     Set    List    Queue  Dequeue   SortedMap
     /
    /
 SortedSet 
            Core Interfaces in Collections

Note that this diagram only shows core interfaces.  
Collection : Root interface with basic methods like add(), remove(), 
             contains(), isEmpty(), addAll(), ... etc.
 
Set : Doesn't allow duplicates. Example implementations of Set 
      interface are HashSet (Hashing based) and TreeSet (balanced
      BST based). LinkedHashSet  . 	Note that TreeSet implements SortedSet.

List : Can contain duplicates and elements are ordered. 
       List Interface is implemented by ArrayList, LinkedList, Vector and Stack classes.

Queue : Typically order elements in FIFO order except exceptions.
LinkedList, ArrayBlockingQueue and PriorityQueue are the most frequently used implementations.


Deque : 
Elements can be inserted and removed at both ends. Allows
both LIFO and FIFO. 
Deque is not thread-safe.

Map : Contains Key value pairs. Doesn't allow duplicates.  Example
      implementation are HashMap and TreeMap. 
      TreeMap implements SortedMap. LinkedHashMap.

The difference between Set and Map interface is that in Set we 
have only keys, whereas in Map, we have key, value pairs.



### What are the use cases and differences of arrays and ArrayLists?

1. Resizable : Array is static in size that is fixed length data structure, One can not change the length after creating the Array object.

ArrayList is dynamic in size . Each ArrayList object  has instance variable capacity which indicates the size of the ArrayList. As elements are added to an ArrayList its capacity grows automatically.


2. Performance : Performance of Array and ArrayList depends on the operation you are performing :

resize() opertation : Automatic resize of ArrayList will slow down the performance as it will use temporary array to copy elements from the old array to new array.
ArrayList is internally backed by Array during resizing  as it calls the native implemented method System.arrayCopy(src,srcPos,dest,destPos,length) .

add() or get() operation : adding an element or retrieving an element from the array or arraylist object has almost same  performance , as for ArrayList object these operations  run in constant time.

3. Primitives :  ArrayList can not contains primitive data types (like int , float , double) it can only contains Object while Array can contain both primitive data types as well as objects.
One get a misconception that we can store primitives(int,float,double) in ArrayList , but it is not true  

Suppose we have ArrayList object ,

ArrayList  arraylistobject = new ArrayList();
arraylistobject.add(23);  // try to add 23 (primitive)

JVM through Autoboxing(converting primitives to equivalent objects internally) ensures that only objects are added to the arraylist object. 
thus , above step internally works like this :

arraylistobject.add( new Integer(23));       
// Converted int primitive to Integer object and added to arraylistobject  

Difference between Array and Arraylist in Java with Example
4. Iterating the values : We can use iterator  to iterate through ArrayList . The iterators returned by the ArrayList class's iterator and listiterator method are fail-fast.  We can use for loop or for each loop to iterate through array .  

5. Type-Safety :  In Java , one can ensure Type Safety through Generics. while Array is a homogeneous data structure , thus it will contain objects of specific class or primitives of specific  data type. In array if one try to store the different data type other than the specified while creating the array object , ArrayStoreException is thrown.

for example :

String temp[] =  new String[2];  // creates a string array of size 2
temp[0] = new Integer(12); // throws ArrayStoreException, trying to add Integer object in String[] 

6. Length :  Length of the ArrayList is provided by the size() method while Each array object has the length variable which returns the length of the array.

for example :
Integer arrayobject[] = new Integer[3];
arraylength= arrayobject.length   ;  //uses arrayobject length variable

ArrayList  arraylistobject = new ArrayList();
arraylistobject.add(12); 
arraylistobject.size();   //uses arraylistobject size method

7. Adding elements : We can insert elements into the arraylist object using the add() method while  in array we insert elements using the assignment operator.

for example :
Integer addarrayobject[] = new Integer[3];
addarrayobject[0]= new Integer(8)   ;  //new object is added to the array object


8. Multi-dimensional :  Array can be multi dimensional , while ArrayList is always single dimensional.

example of multidimensional array:

Integer addarrayobject[][] = new Integer[3][2];
addarrayobject[0][0]= new Integer(8)  

### What is mutable and immutable string ?
In java, string objects are immutable. Immutable simply means unmodifiable or unchangeable. Once string object is created its data or state can't be changed but a new string object is created.

Let's try to understand the immutability concept by the example given below:

	class Testimmutablestring{  
	 public static void main(String args[]){  
	   String s="Sachin";  
	   s.concat(" Tendulkar");//concat() method appends the string at the end  
	   System.out.println(s);//will print Sachin because strings are immutable objects  
	 }  
	}  

	Output:Sachin

 Here Sachin is not changed but a new object is created with sachintendulkar. but s reference variable still refers to "Sachin" not to "Sachin Tendulkar".

But if we explicitely assign it to the reference variable, it will refer to "Sachin Tendulkar" object.
For example:

	class Testimmutablestring1{  
	 public static void main(String args[]){  
	   String s="Sachin";  
	   s=s.concat(" Tendulkar");  
	   System.out.println(s);  
	 }  
	} 

	Output:Sachin Tendulkar
	

String is immutable for several reasons, here is a summary:

- Security: parameters are typically represented as String in network connections, database connection urls, usernames/passwords etc. If it were mutable, these parameters could be easily changed.

- Synchronization and concurrency: making String immutable automatically makes them thread safe thereby solving the synchronization issues.

- Caching: when compiler optimizes your String objects, it sees that if two objects have same value (a="test", and b="test") and thus you need only one string object (for both a and b, these two will point to the same object).

- Class loading: String is used as arguments for class loading. If mutable, it could result in wrong class being loaded (because mutable objects change their state).
	
### What is the difference between String and String Builder ? 

- String vs StringBuffer vs StringBuilder
- String is immutable whereas StringBuffer and StringBuider are mutable classes.
- StringBuffer is thread safe and synchronized whereas StringBuilder is not, thats why StringBuilder is more faster than StringBuffer.
- String concat + operator internally uses StringBuffer or StringBuilder class.
- For String manipulations in non-multi threaded environment, we should use StringBuilder else use StringBuffer class.


### What are the use cases and differences of a HashSet and a TreeSet? 

### Difference between HashSet and TreeSet 

1. Ordering : HashSet stores the object in random order . There is no guarantee that the element we inserted first in the HashSet will be printed first in the output . For example   


import java.util.HashSet;

public class HashSetExample {
    
    public static void main(String[] args) {
        
        HashSet<String>  obj1= new HashSet<String>();
        obj1.add("Alive");
        obj1.add("is");
        obj1.add("Awesome");
        System.out.println(obj1);        
    }    
} 
 
OUTPUT : [is, Awesome, Alive]   

Elements are sorted according to the natural ordering of its elements in TreeSet. If the objects can not be sorted in natural order than use compareTo() method to sort the elements of TreeSet object .

import java.util.TreeSet;

public class TreeSetExample {
    
    public static void main(String[] args) {
        
        TreeSet<String>  obj1= new TreeSet<String>();
        obj1.add("Alive");
        obj1.add("is");
        obj1.add("Awesome");
        System.out.println(obj1);
        
    }
    
}
 
OUTPUT : [Alive, Awesome, is]   

2. Null value :   HashSet can store null object while TreeSet does not allow null object. If one try to store null object in TreeSet object , it will throw Null Pointer Exception.

3. Performance : HashSet take constant time performance for the basic operations like add, remove contains and  size.While TreeSet guarantees log(n) time cost for the basic operations (add,remove,contains).

4. Speed : HashSet is much faster than TreeSet,as performance time of HashSet is constant against the log time of TreeSet for most operations (add,remove ,contains and size) . Iteration performance of HashSet mainly depends on the load factor and initial capacity parameters. 

5. Internal implementation :  As we have already discussed How hashset internally works in java thus, in one line HashSet are internally backed by hashmap. While TreeSet is backed by a  Navigable  TreeMap. 

Difference between HashSet and TreeSet in Java with Example

6. Functionality :    TreeSet is rich in functionality as compare to HashSet. Functions like pollFirst(),pollLast(),first(),last(),ceiling(),lower() etc. makes TreeSet easier to use than HashSet. 

7. Comparision : HashSet uses equals() method for comparison in java while TreeSet uses compareTo() method for maintaining ordering .

To whom priority is given TreeSet comparator or Comparable.compareTo() .

Suppose there are elements in TreeSet which can be naturally sorted by the TreeSet , but we also added our own sorting method by implementing Comparable interface compareTo() method .
Then to whom priority is given.

Answer to the above question is that the Comparator passed into the TreeSet constructor has been given priority.
According to Oracle Java docs 

public TreeSet(Comparator comparator)

Constructs a new, empty tree set, sorted according to the specified comparator.

Parameters:
comparator - the comparator that will be used to order this set. If null, the natural ordering of the elements will be used.


### Similarities Between HashSet and TreeSet

1. Unique Elements :   Since HashSet and TreeSet both implements Set interface . Both are allowed to store only unique elements in their objects. Thus there can never be any duplicate elements inside the HashSet and TreeSet objects.

2. Not Thread Safe : HashSet and TreeSet both are not synchronized or not thread safe.HashSet and TreeSet, both implementations are not synchronized. If multiple threads access a hash set/ tree set concurrently, and at least one of the threads modifies the set, it must be synchronized externally.

3. Clone() method copy technique:  Both HashSet and TreeSet uses shallow copy technique to create a clone of  their objects .

4. Fail-fast Iterators :  The iterators returned by this class's  method are fail-fast: if the set is modified at any time after the iterator is  created, in any way except through the iterator's own  remove method, the iterator will throw a  ConcurrentModificationException.  Thus, in the face of concurrent modification, the iterator fails quickly and cleanly, rather than risking arbitrary, non-deterministic behavior at   an undetermined time in the future.


### When to prefer TreeSet over HashSet

1.  Sorted unique elements are required instead of unique elements.The sorted list given by TreeSet is always in ascending order.

2.   TreeSet has greater locality than HashSet.

If two entries  are near by in the order , then TreeSet places them near each other in data structure and hence in memory, while HashSet spreads the entries all over memory  regardless of the keys they are associated to. 
     
As we know Data reads from the hard drive takes much more latency time than data read from the cache or memory. In case data needs to be read from hard drive than prefer TreeSet as it has greater locality than HashSet.

3. TreeSet uses Red- Black tree algorithm underneath to sort out the elements. When one need to perform read/write operations frequently , then TreeSet is a good choice.
   
Thats it for the difference between HashSet and TreeSet , if you have any doubts then please mention in the comments.


Multithreading in Java
Multithreading is a Java feature that allows concurrent execution of two or more parts of a program for maximum utilization of CPU. Each part of such program is called a thread. So, threads are light-weight processes within a process.

Threads can be created by using two mechanisms :
1. Extending the Thread class
2. Implementing the Runnable Interface

		class MultithreadingDemo extends Thread 
		{ 
			    public void run() 
			    { 
				try
				{ 
				    // Displaying the thread that is running 
				    System.out.println ("Thread " + 
					  Thread.currentThread().getId() + 
					  " is running"); 

				} 
				catch (Exception e) 
				{ 
				    // Throwing an exception 
				    System.out.println ("Exception is caught"); 
				} 
			} 
		} 

		// Main Class 
		public class Multithread 
		{ 
		    public static void main(String[] args) 
		    { 
			int n = 8; // Number of threads 
			for (int i=0; i<8; i++) 
			{ 
			    MultithreadingDemo object = new MultithreadingDemo(); 
			    object.start(); 
			} 
		    } 
		} 




		class MultithreadingDemo implements Runnable 
		{ 
		    public void run() 
		    { 
			try
			{ 
			    // Displaying the thread that is running 
			    System.out.println ("Thread " + 
						Thread.currentThread().getId() + 
						" is running"); 

			} 
			catch (Exception e) 
			{ 
			    // Throwing an exception 
			    System.out.println ("Exception is caught"); 
			} 
		    } 
		} 

		// Main Class 
		class Multithread 
		{ 
		    public static void main(String[] args) 
		    { 
			int n = 8; // Number of threads 
			for (int i=0; i<8; i++) 
			{ 
			    Thread object = new Thread(new MultithreadingDemo()); 
			    object.start(); 
			} 
		    } 
		}



### Thread Class vs Runnable Interface

If we extend the Thread class, our class cannot extend any other class because Java doesn’t support multiple inheritance. But, if we implement the Runnable interface, our class can still extend other base classes.
We can achieve basic functionality of a thread by extending Thread class because it provides some inbuilt methods like yield(), interrupt() etc. that are not available in Runnable interface

### ThreadPool in Java?

A thread pool reuses previously created threads to execute current tasks and offers a solution to the problem of thread cycle overhead and resource thrashing. Since the thread is already existing when the request arrives, the delay introduced by thread creation is eliminated, making the application more responsive.

Executor Thread Pool Methods

Method                         Description
- newFixedThreadPool(int)           Creates a fixed size thread pool.
- newCachedThreadPool()             Creates a thread pool that creates new 
                                  threads as needed, but will reuse previously 
                                  constructed threads when they are available
- newSingleThreadExecutor()         Creates a single thread. 


	// Java program to illustrate 
	// ThreadPool 
	import java.text.SimpleDateFormat; 
	import java.util.Date; 
	import java.util.concurrent.ExecutorService; 
	import java.util.concurrent.Executors; 

	// Task class to be executed (Step 1) 
	class Task implements Runnable 
	{ 
		private String name; 

		public Task(String s) 
		{ 
			name = s; 
		} 

		// Prints task name and sleeps for 1s 
		// This Whole process is repeated 5 times 
		public void run() 
		{ 
			try
			{ 
				for (int i = 0; i<=5; i++) 
				{ 
					if (i==0) 
					{ 
						Date d = new Date(); 
						SimpleDateFormat ft = new SimpleDateFormat("hh:mm:ss"); 
						System.out.println("Initialization Time for"
								+ " task name - "+ name +" = " +ft.format(d)); 
						//prints the initialization time for every task 
					} 
					else
					{ 
						Date d = new Date(); 
						SimpleDateFormat ft = new SimpleDateFormat("hh:mm:ss"); 
						System.out.println("Executing Time for task name - "+ 
								name +" = " +ft.format(d)); 
						// prints the execution time for every task 
					} 
					Thread.sleep(1000); 
				} 
				System.out.println(name+" complete"); 
			} 

			catch(InterruptedException e) 
			{ 
				e.printStackTrace(); 
			} 
		} 
	} 
	public class Test 
	{ 
		// Maximum number of threads in thread pool 
		static final int MAX_T = 3;			 

		public static void main(String[] args) 
		{ 
			// creates five tasks 
			Runnable r1 = new Task("task 1"); 
			Runnable r2 = new Task("task 2"); 
			Runnable r3 = new Task("task 3"); 
			Runnable r4 = new Task("task 4"); 
			Runnable r5 = new Task("task 5");	 

			// creates a thread pool with MAX_T no. of 
			// threads as the fixed pool size(Step 2) 
			ExecutorService pool = Executors.newFixedThreadPool(MAX_T); 

			// passes the Task objects to the pool to execute (Step 3) 
			pool.execute(r1); 
			pool.execute(r2); 
			pool.execute(r3); 
			pool.execute(r4); 
			pool.execute(r5); 

			// pool shutdown ( Step 4) 
			pool.shutdown();	 
		} 
	} 

### Risks in using Thread Pools

1. Deadlock : While deadlock can occur in any multi-threaded program, thread pools introduce another case of deadlock, one in which all the executing threads are waiting for the results from the blocked threads waiting in the queue due to the unavailability of threads for execution.

2. Thread Leakage :Thread Leakage occurs if a thread is removed from the pool to execute a task but not returned to it when the task completed. As an example, if the thread throws an exception and pool class does not catch this exception, then the thread will simply exit, reducing the size of the thread pool by one. If this repeats many times, then the pool would eventually become empty and no threads would be available to execute other requests.

3. Resource Thrashing :If the thread pool size is very large then time is wasted in context switching between threads. Having more threads than the optimal number may cause starvation problem leading to resource thrashing as explained.

Important Points

Don’t queue tasks that concurrently wait for results from other tasks. This can lead to a situation of deadlock as described above.
Be careful while using threads for a long lived operation. It might result in the thread waiting forever and would eventually lead to resource leakage.

The Thread Pool has to be ended explicitly at the end. If this is not done, then the program goes on executing and never ends. Call shutdown() on the pool to end the executor. If you try to send another task to the executor after shutdown, it will throw a RejectedExecutionException.

One needs to understand the tasks to effectively tune the thread pool. If the tasks are very contrasting then it makes sense to use different thread pools for different types of tasks so as to tune them properly.

### What is Handler / Message Queue : 

Message queue  : Android maintains message queue which is always populated with tasks that needs to update the UI , Task could be as simple as rendering button, doing something on click of button,

You going to execute the task that are there in queue ? 
looper : For this we have another thread which under constant loop that keeps on executing any task that is there in message queue. Since this thread under constant loop and  it is called looper. 

UI Looper thread : So in our case, since we want to update UI , the UI thread itself is under a constant loop and it is trying to execute any task that you put in this particular message queue. 

Handler  : We have thread and thread wants to put a task in this particular message queue, it is not possible to put that directly, thread cannot directly put a task into message queue, for that we use something called a handler. Thread gives task that it wants to put into queue to the handler. And Handler will be having reference to message queue. And it will place that particular task in the message queue.


### What if we want to create our own custom looper ? 
We will create own thread that behave like looper , looper thread will be able host tasks that it wants to execute.  
From the UI thread , we will launch new thread , this new thread basically uses handler and then put the task to custom looper thread we have created 

	Public class LooperThread extends Thread { 

		Public void run() { 

			Looper.prepare();

			Looper.loop();	
		}
	}

Typically what happens in thread, we get into the run method and execute what ever there in Run method and exit out of run method, we don’t want that to happen, we want to run this thread continuously in the infinite loop and keep on executing things that we give to execute.

Now with this thread, we have to make sure of creating pretty much every thing  that is creating thread, converting thread into looper, even having handler in that particular looper thread which can handle task to handle it , now the questions is, is there any ready made API available from android that I can use to implement looper thread. Answer is , HandlerThread 

	Public class CustomHandlerThread extends HandlerThread { 

		Public Handler mHandler;

		Protected void onLooperPrepared() {
			Super.onLooperPrepared();
			mHandler = new Handler() {


	@Override
	Public void HandleMessage(Message msg) {
		Super.handleMessage(Msg);
		Log.i();
	}

			}
		}
	} 



To update UI using Handler thread : 

	customHandlerThread.mHandler.post(new Runnable(){

		@Override
		Public void run() {

			}

		}
	})


You can use LooperThread OR HandlerThread , its up to you what you want to use. 

How to stop the looper ??

looperThread.handler.getLooper().quit();
customerHandlerThread.getLooper().quit();

### Explain event-driven programming in Java 
### How can you typecast in Java? 
### Explain Java's try-catch-finally paradigm
### Build Tools
### Have you used any Ant, Maven, Gradle features for your project?

### Core Android

### How does the Android notification system work?

From what I've heard during an Android developers conference in Israel:

There is simply a TCP socket waiting in accept mode on a cloud Google server. The TCP connection had been initiated by the Google Play application. That's why Google Play must be installed on the device for making Google Cloud Messaging (GCM) (formerly Android Cloud to Device Messaging Service - C2DM) work.

When this TCP client socket receives some message, the message contains information such as the package name of the application it should be addressed to, and of course - the data itself. This data is parsed and packed into an intent that is broadcast and eventually received by the application.

The TCP socket stays open even when the device's radio state turns into "idle" mode. Applications don't have to be running to receive the intents.

More information at http://developer.android.com/google/gcm/gcm.html

### How can two distinct Android apps interact? (several answers)

At the simplest level there are two different ways for apps to interact on Android: via Intents, passing data from one application to another; and through Services, where one application provides functionality for others to use. There are different ways to utilize both methods, depending on what you want to accomplish and what technical challenges you face. This is a brief overview that wil l avoid delving into the technical aspects.

Intents
An Intent describes an action to be performed, such as opening a file, dialing a phone number, or turning airplane mode on. The first two are actions that can be initiated by user apps, while the latter is a system-wide notification that any app can act on. For example, if you tap on a PDF in a file browser it will probably try to start up a document viewer app so you can read it. In this case, the file browser is using an Intent to start an Activity to view the file and passing the path to the file as part of the Intent's data. The system receives the Intent and opens a different app that has registered with the system that it can view PDF files—or if you have multiple apps that are capable, you might be presented with a list to choose from. Additionally, should an app want to run an action in the background rather than requiring any user interaction, an Intent can instead be used to start a Service rather than an Activity. Any app can also utilize broadcast receivers, which will listen to system-wide messages. An app might want stop trying to connect to the Internet once airplane mode is engaged, so by registering a BroadcastReceiver with the system to listen for an Intent with that specific action, the app can tell when it happens and act on it. Intents can also carry extra data via a Bundle, which can handle any kind of serializable data. As the data in a Bundle is stored using arbitrary keys, this is generally only useful if the receiving app knows the context for the incoming data.

Services
One feature of a Service is to perform an action in the background as mentioned above, similar to an Activity but without user interface components. The other primary use of a Service is to provide bindings, which lets an app expose part of its functionality to other applications. Other apps bound to the service will have a persistent connection that lets them call methods defined on the Service, which can directly interact with other parts of the app. Using an example app that controls a VPN connection on the device, a Service provided by the app could allow other applications to get information about the VPN connection, its current state, or even turn the connection on or off. While toggling the connection could also be handled by a simple Intent action, having access to the other information provided by the Service can allow apps to intelligently interact with it.

Describe Activities.
An activity represents a single screen with a user interface,in-short Activity performs actions on the screen. For example, an email application might have one activity that shows a list of new emails, another activity to compose an email, and another activity for reading emails. If an application has more than one activity, then one of them should be marked as the activity that is presented when the application is launched.

### What are the four states of the Activity Lifecycle? 
[active/running, paused, stopped, destroyed]

### What are the seven callback methods of an Activity used to perform operations when the Activity transitions between states? 

[onCreate(), onStart(), onResume(), onPause(), onStop(), onRestart(), onDestroy()]

### What is the difference between a fragment and an activity? Explain the relationship between the two. 

Activity : 
Activities are one of the fundamental building blocks of apps on the Android platform. They serve as the entry point for a user's interaction with an app. When one app invokes another, the calling app invokes an activity in the other app, rather than the app as an atomic whole. In this way, the activity serves as the entry point for an app's interaction with the user.

An activity provides the window in which the app draws its UI.
To use activities in your app, you must register information about them in the app’s manifest, and you must manage activity lifecycles appropriately

Typically, one activity in an app is specified as the main activity, which is the first screen to appear when the user launches the app.
Over the course of its lifetime, an activity goes through a number of states.

### What is a Fragment?

A Fragment represents a behavior or a portion of user interface in an Activity. You can combine multiple fragments in a single activity to build a multi-pane UI and reuse a fragment in multiple activities. You can think of a fragment as a modular section of an activity, which has its own lifecycle, receives its own input events, and which you can add or remove while the activity is running.

Lifecycle methods are hosted by are hosted by hosting activity.
Lifecycle of a fragment

### When to use fragment and when to use activity ? 
Fragments are encapsulated parts of an activity , when you build up your application, when your activity starts getting too big, you need to start breaking up into fragment effectively. 

### When to use fragment and views ?
Views are the nuts and bolts of your UI , Activities and fragments are life cycle constructs that basically provides plugin points of contact with rest of the system that tells you what’s going on. 


### Activity life cycle

- protected void onCreate(Bundle savedInstanceState);
	Called when the activity is first created. This is where you should do all of your normal static set up: create views, bind data to lists, etc. This method also provides you with a Bundle containing the activity's previously frozen state, if there was one.Always followed by onStart().


- protected void onRestart(); 
	Called after your activity has been stopped, prior to it being started again. Always followed by onStart()

 - protected void onStart();
	Called when the activity is becoming visible to the user.
Followed by onResume() if the activity comes to the foreground, or onStop() if it becomes hidden

- protected void onResume();
	Called when the activity will start interacting with the user. At this point your activity is at the top of the activity stack, with user input going to it.
Always followed by onPause().

- protected void onPause();
	Called when the system is about to start resuming a previous activity. This is typically used to commit unsaved changes to persistent data, stop animations and other things that may be consuming CPU, etc. Implementations of this method must be very quick because the next activity will not be resumed until this method returns.
	Followed by either onResume() if the activity returns back to the front, or onStop() if it becomes invisible to the user.

- protected void onStop();
	Called when the activity is no longer visible to the user, because another activity has been resumed and is covering this one. This may happen either because a new activity is being started, an existing one is being brought in front of this one, or this one is being destroyed.
	Followed by either onRestart() if this activity is coming back to interact with the user, or onDestroy() if this activity is going away.

 - protected void onDestroy();
	The final call you receive before your activity is destroyed. This can happen either because the activity is finishing (someone called finish() on it), or because the system is temporarily destroying this instance of the activity to save space. You can distinguish between these two scenarios with the isFinishin() method.
 }

### What is the difference between Serializable and Parcelable? Which is the best approach in Android? 

When starting on Android, we all learn that we cannot just pass object references to activities and fragments, we have to put those in an Intent / Bundle.

Looking at the api, we realize that we have two options, we can either make our objects Parcelable or Serializable. As Java developers, we already know of the Serializable mechanism, so why bother with Parcelable?

To answer this, lets take a look at both approaches.

	// access modifiers, accessors and constructors omitted for brevity
	public class SerializableDeveloper implements Serializable
	    String name;
	    int yearsOfExperience;
	    List<Skill> skillSet;
	    float favoriteFloat;

	    static class Skill implements Serializable {
		String name;
		boolean programmingRelated;
	    }
	}

The beauty of serializable is that you only need to implement the Serializable interface on a class and its children. It is a marker interface, meaning that there is no method to implement, Java will simply do its best effort to serialize it efficiently.

The problem with this approach is that reflection is used and it is a slow process. This mechanism also tends to create a lot of temporary objects and cause quite a bit of garbage collection.

Parcelable,

According to google engineers, this code will run significantly faster. One of the reasons for this is that we are being explicit about the serialization process instead of using reflection to infer it. It also stands to reason that the code has been heavily optimized for this purpose.

However, it is obvious here that implementing Parcelable is not free. There is a significant amount of boilerplate code and it makes the classes harder to read and maintain.

### What are "launch modes"?
There are four launch modes for activity. They are:

1. standard
2. singleTop
3. singleTask
4. singleInstance

In the AndroidManifest you can use “launchMode” attribute inside the <activity> element to declare the activity’s launch mode like-

<activity android:launchMode = [“standard” | “singleTop” | “singleTask” | “singleInstance”] ../>
Now let’s look at the differences between launch modes.

1. standard
	This is the default launch mode of an activity (If not specified). It creates a new instance of an activity in the task from 	which it was started. Multiple instances of the activity can be created and multiple instances can be added to the same or different 	tasks. In other words you can create the same activity multiple times in the same task as well as in different tasks.

	<activity android:launchMode=”standard” />
	Example:
	Suppose you have A, B, C and D activities and your activity B has “launch mode = standard”. Now you again launching activity B 

	State of Activity Stack before launch B
	A -> B -> C -> D

	State of Activity Stack after launch B
	A -> B -> C -> D -> B

2. singleTop
	In this launch mode if an instance of activity already exists at the top of the current task, a new instance will not be created and Android system will route the intent information through onNewIntent(). If an instance is not present on top of task then new instance will be created.

	Using this launch mode you can create multiple instance of the same activity in the same task or in different tasks only if the same instance does not already exist at the top of stack.

	<activity android:launchMode=”singleTop” />
	Example:
	Case 1:
	Suppose you have A, B and C activities and your activity D has “launch mode = singleTop”. Now you launching activity D -

	State of Activity Stack before launch D
	A -> B -> C

	State of Activity Stack after launch D activity
	A -> B -> C -> D (Here D launch as usual)

	Case 2:
	Suppose you have A, B, C and D activities and your activity D has “launch mode = singleTop”. Now you again launching activity D -

	State of Activity Stack before launch D
	A -> B -> C -> D

	State of Activity Stack after launch D activity
	A -> B -> C -> D (Here old instance gets called and intent data route through onNewIntent() callback)

3. singleTask
	In this launch mode a new task will always be created and a new instance will be pushed to the task as the root one. If an instance of activity exists on the separate task, a new instance will not be created and Android system routes the intent information through onNewIntent() method. At a time only one instance of activity will exist.

	<activity android:launchMode=”singleTask” />
	Example:
	Case 1:
	Suppose you have A, B and C activities and your activity D has “launch mode = singleTask”. Now you launching activity D -

	State of Activity Stack before launch D
	A -> B -> C

	State of Activity Stack after launch D activity
	A -> B -> C -> D (Here D launch as usual)

	Case 2:
	Suppose you have A, B, C and D activities and your activity B has “launch mode = singleTask”. Now you again launching activity B-

	State of Activity Stack before launch D
	A -> B -> C -> D

	State of Activity Stack after launch B activity
	A -> B (Here old instance gets called and intent data route through onNewIntent() callback)

	Also notice that C and D activities get destroyed here.

4. singleInstance
	This is very special launch mode and only used in the applications that has only one activity. It is similar to singleTask except that no other activities will be created in the same task. Any other activity started from here will create in a new task.

	<activity android:launchMode=”singleInstance” />
	Example:
	Case 1:
	Suppose you have A, B and C activities and your activity D has “launch mode = singleInstance”. Now you launching activity D -

	State of Activity Stack before launch D
	A -> B -> C

	State of Activity Stack after launch D activity
	Task1 — A -> B -> C
	Task2 — D (here D will be in different task)

	Now if you continue this and start E and D then Stack will look like-

	Task1 — A -> B -> C -> E
	Task2 — D

	Case 2:
	Suppose you have A, B, C activities in one task and activity D is in another task with “launch mode = singleInstance”. Now you again launching activity D-

	State of Activity Stack before launch D
	Task1 — A -> B -> C

	Task2 — D
	State of Activity Stack after launch B activity
	Task1 — A -> B -> C
	Task2 — D (Here old instance gets called and intent data route through onNewIntent() callback)


### What are Intents?

Intents are asynchronous messages which allow application components to request functionality from other Android components. Intents allow you to interact with components from the same applications as well as with components contributed by other applications. For example, an activity can start an external activity for taking a picture.


### What is an Implicit Intent? What is an Explicit Intent? 

There are two types of intents:

Explicit intents specify which application will satisfy the intent, by supplying either the target app's package name or a fully-qualified component class name. You'll typically use an explicit intent to start a component in your own app, because you know the class name of the activity or service you want to start. For example, you might start a new activity within your app in response to a user action, or start a service to download a file in the background.

Implicit intents do not name a specific component, but instead declare a general action to perform, which allows a component from another app to handle it. For example, if you want to show the user a location on a map, you can use an implicit intent to request that another capable app show a specified location on a map.

Describe three common use cases for using an Intent.

Common use cases for using an Intent include:

To start an activity: You can start a new instance of an Activity by passing an Intent to startActivity() method.

	Intent intent = new Intent(this, DisplayMessageActivity.class);
	EditText editText = (EditText) findViewById(R.id.editText);
	String message = editText.getText().toString();
	intent.putExtra(EXTRA_MESSAGE, message);
	startActivity(intent);

2. To start a service: You can start a service to perform a one-time operation (such as download a file) by                  passing an Intent to startService().

3. To deliver a broadcast: You can deliver a broadcast to other apps by passing an Intent to sendBroadcast(),           sendOrderedBroadcast(), or sendStickyBroadcast()

### What is a Service?

Key points :
Service is one of the four major component in android. other being content provider, Activity, Broadcast receiver.
Service is used to create long running operation in background, here the term background is important. when i say background, it could be something like downloading large file, downloading multiple images.

Services doesn't have user interface, it is obvious that user may not be interested in waiting something to get done for longer period. 
Service doesn’t accommodate it’s own thread, it doesn’t span with new thread , we need declare another thread otherwise it runs on UI and end up giving application not responding error. 

Service you created needs to be mention in android manifest 


### Should you use a service or a thread?

A service is simply a component that can run in the background, even when the user is not interacting with your application, so you should create a service only if that is what you need.

You can still consider AsyncTask and HandlerThread for doing the same as service but AsyncTash or HandlerThread are closely coupled with activity. life time of these threads is on activity life cycle / Application context. if you want to run some operations even when application process is not live OR application activity is not live then service is needed. 


### Types of services:

Foreground :
A foreground service performs some operation that is noticeable to the user. typical example is , an audio app would use a foreground service to play an audio track. Foreground services must display a Notification. Foreground services continue running even when the user isn't interacting with the app.

Background : 
A background service performs an operation that isn't directly noticed by the user. For example, if an app used a service to compact its storage, that would usually be a background service.

Bound : 
There might be situation where you want to check result of services , where you want receive / Send updated results from service to other component . in which bound service is needed.

A service is bound when an application component binds to it by calling bindService(). A bound service offers a client-server interface that allows components to interact with the service, send requests, receive results, and even do so across processes with interprocess communication (IPC)


### Implementation of service : 

Class which extend services becomes service class. on extending service, there are certain methods to be override in the class

- OnCreate() - The system invokes this method to perform one-time setup procedures when the service is initially created

- OnBind() - The system invokes this method by calling bindService() when another component wants to bind with the service (such as to perform RPC). 

- OnDestroy() - to clean up any resources such as threads, registered listeners, or receivers. This is the last call that the service receives.

- OnStartCommand () - The system invokes this method by calling startService(), to stop service we say that stopSelf() or stopServices().


### Android system force-stops a service : 

Let’s assume I have app which is some thing called grocery list , and I have open another app on top of grocery app, and again another app and so on. as I keep on starting multiple apps there may arise a situation where in resource crunch situation will happen and android may actually decide to kill your app which is not running in the foreground. In case I had a service that was running in my app which is running in background then android will not try to kill that particular application because services is always gets a high priority. But that doesn’t mean that just because you keep service and it will not killed, if the resource crunch actually do happen and resource crunch is very severe then android operating system may actually decides to even kill the app.

Later point in time as the resource become available , android operating system will have enough resources to host the services that had been killed earlier. 

Now the question is what would happen to the service that had been killed ?

-If the system kills your service, it restarts it as soon as resources become available, but this also depends on the value that you return from onStartCommand().

Start_sticky - Auto restart , null intent
start_not_sticky - no auto restart, with intent started 
start_redeliver_intent -  yes - intent 

You can ensure that your service is available to only your app by including the android:exported attribute and setting it to false . 

Users can see what services are running on their device. If they see a service that they don't recognize or trust, they can stop the service. In order to avoid having your service stopped accidentally by users, you need to add the android:description attribute to the <service> element in your app manifest. In the description, provide a short sentence explaining what the service does and what benefits it provides.


### Intent Service

It is subclass of service The IntentService class does the following:

It uses its own worker thread to handle all of its start request one at time. This is the best option if you don't require that your service handle multiple requests simultaneously.

Work requests run sequentially. If an operation is running in an IntentService, and you send it another request, the request waits until the first operation is finished.All requests are handled on a single worker thread.

An operation running on an IntentService can't be interrupted. IntentService also needs an entry in your application manifest. 

## What is a Content Provider and what is it typically used for?
The Android framework enforces a robust and secure data sharing model. Applications are not allowed direct access to other application’s internal data. Two classes in the package help enforce this requirement: the ContentResolver and the ContentProvider.

In typical android system, each app is hosted in separate process , each process might be having separate data , that is app one could be having separate data base. There could be scenario where in app two wants to connects to app one data base . usually this not possible because of database/Data maintained by app1 is private to that particular app . the only legal mechanism is app2 needs to request to the data from the app1 and app1 respond back with data . now obivious question is , how do we make sure app1 exposes data in secure manner that’s where a new component come into picture called as content provider. App2 uses API called content resolver using which it will hit app one database OR data . content provider which is there at app1 is respond back with data format called cursor. It is inter process communication 

Content provider does is it provides kind of abstraction from handling this inter processor communication. 

In real world scenario, the app one could be a contact app which contains different contact stored by the user in the device and app two could be a what’s app OR skype app which is trying to access the contact stored in the device . it doesn’t really matter how the contacts are stored in contacts app, it could be stored in database and file or could be stored in JSON file and XML file. 

Content provider abstract the way these two communication happens .  

To actually hit correct content provider , you need to know uniform resource identifier. Content resolver provide you certain method using which you can perform CRUD operations. Basically create, receive, update and delete operations . you can also perform the batch operations . 

Basically it provides you mechanism to connect to remote data as you are doing data base operations . 

Coming back to cursor, content return data in tabular form containing rows and column , cursor is the API which allows you to traverse through rows defined in that tabular form . 

getContentResolver() return content resolver object  
getContentResolver().query()(<Content provider>.Content.URI, mProjection (String which respresent column that you want carry from content provider) , mSelectionClause(Where clause), mSelectionArgs , mSortOrder )

Requesting for data
Initialise UI with data 
Happens in UI thread

Load the data from content provider is always happens in UI thread if explicitly not taken care . it is not good idea to load data on the mail if data is very huge, it leads to application is not responding error. One of solving this problem is by using thread or aSyncTask . android resolves this another build in API called loader Or cursor Loaders which can be used load the data from content provider in an separate worker thread. 

Each activity can have single or multiple set of loader . Loader manager has interface called loader callbacks . your activity has to implement to loader callbacks . when you implement this interface . you load onCreate loader , onloadfinish(), onLoaderReset().

Loaders ensure that all cursor operations are done asynchronously, thus eliminating the possibility of blocking the UI thread. Further, when managed by the LoaderManager, Loaders retain their existing cursor data across the activity instance (for example, when it is restarted due to a configuration change), thus saving the cursor from unnecessary, potentially expensive re-queries. As an added bonus, Loaders are intelligent enough to monitor the underlying data source for updates, re-querying automatically when the data is changed.

Advantages of having loaders is that, when there is a change in other applications, it automatically load new content in other application when resuming activity . 


### Broad Cast Receiver : 
Usually in android operating system you will encounter lot of different type of events that are occurring, events would be battery low, incoming call, incoming SMS, Wifi-Availability, Bluetooth device connected, Charger disconnected . 
Probably you will encounter the scenario where in you want to respond to any of these events that is happening in system. 
For example , if in case of battery scenario, you may want to stop your application to stop pulling backend data pulling mechanism, because that is unnecessary drain the battery. 

You basically want mechanism to listen these events, for that we need listener , this listener only listen if it register to only to this particular events.  Listener is nothing but the broadcast listener . 

There are two ways to register broadcast receiver-

Steps to create : 

1. Extend class with broadcastlistener 
2. Give permission in manifest
3. Declare class in manifest <Receiver > 
4. Provide intent filter must be declare with what event is

Two types of broad cast listener : 

Registering at manifest file (global broadcast)

OR

Through the code , why through code, to avoid listener when there app is in background 

	onStart() {
	IntentFilter intentFilter = new IntentFilter(“SMS”);
	RegisterBroadCastReceiver(myBroadCastReceiver,  intentFilter);
	}

	onStop() {
		Unregister();
	}

 
 What if I want make my own board cast listener rather system generated broadcast?
 
Risk : Any app XYZ app can trigger broadcast , to avoid that make your broad cast to 
Android:exported = false

Reverse scenario , you don’t want any broadcast to happen outside the app, for that you make localbroadcastManager - If you don't need to send broadcasts to components outside of your app

	LocalBroadcastManager.getInstance(this).registerReceiver(mMessageReceiver,
	new IntentFilter("custom-event-name"));


Android Oero limitation : 
1. Registering in android manifest file is deprecated in oreo, it doesn’t work instead  it is to create dynamically ,you have to register broadcast dynamically in onStart();

2. Order broad cast receiver : it is not only the case that you always have one broadcast listener in the app , you may have list of broadcast listener to listen to event and to respond , in that scenario , , what if you want to control in which series these particular broad cast get trigger ? There you need Order broad cast listener . 

Notes : 
BR runs on UI thread. So BR should be done more than anything which takes 10 sec
BR is not suited for asynchronous calls.
Never Bind to service from the Broadcast receiver, how ever you can start service from broadcast receiver. 
Broadcast receiver are prone to hack , you have to always secure them. 
SetExported:false
Use LocalbroadcastManager. 




### Android O limitation on services : 
### what happens when you do start services when your not there in forground services? 

you will get illagal state exception. basically is not the way to start background services anymore. this kind of big deal in android oreo . there are some very practical ways in which this is softened up. one of that is grace period . services continue to run on for a while once you lose your foreground status  

Application can no longer freely execute background services . Idea here is to stop thinking about services and start thinking about job scheduler Or firebase Job dispatcher for the kind of work you currently give to services . 

Starting services in response to broadcast receiver is no longer be possible. 
The idea behind these changes is fundamentally that, if expansive or potential expensive work is being done on behalf of the users, user should be aware of that .  it should be visible to user. if you are doing things that cost user data, battery,  ram . user should sort of say , hey i know your doing this, i approve . This is making my app experience really quite good. Keep doing it . we don't want expensive work sort of happening quietly in a clandestine manner without the user approval   


Before Android 8.0, Android apps would start a service that ran almost indefinitely, even when the app was in the background. This service can be handy for the app, and easy for the developer to implement, but may also have an impact on device experience.
Imagine a scenario where many applications want to perform work when a device is plugged in to charge. When this happens, Android dispatches the android.intent.action.ACTION_POWER_CONNECTED intent. All apps registered to respond to that intent will start up, demanding RAM, CPU time, and bandwidth. Consequentially, it is possible these simultaneous demands may exceed the available space on the device and cause it to slow down. At this point, all a user knows is that they plugged in their device and it started exhibiting sluggish, unresponsive behavior and may assume something is wrong with their phone or memory.

### Android and the JobScheduler

Android 8.0 has introduced new background execution limits that dramatically change how services work. When applications move into the background, any services they start will be granted several minutes to complete their work before the operating system terminates them. 
	
The Android Framework JobScheduler is an API designed to run jobs—discrete, distinct units of work—in the background of various apps. The JobScheduler schedules which jobs will run at appropriate times according to conditions that can be set by the application. Going back to our original example above, the JobScheduler may schedule the jobs so that they run one after another, instead of all at once.

Scheduling : 
The ability to schedule and queue jobs make the JobScheduler perfect for tasks that are traditionally handled by long-running services, such as:

Downloading a file, but only when the device is connected to an unmetered (free) network.
When charging a device, make a series of thumbnail images from a collection of larger images.

If connected to the network, call a method on a web service using an exponential backoff algorithm between unsuccessful web service calls.

Classes
There are three important classes in the JobScheduler API:

JobScheduler: A system service that will run jobs scheduled by apps.

JobService: A class extended by applications and contains the code that runs as part of a job. The code for each job is contained in a class that extends the JobService class and requests the android.permission.BIND_JOB_SERVICEpermission.

JobInfo: Holds information about the job that the JobScheduler needs in order to run a JobService. The JobInfo will tell the JobScheduler which JobService type to use and which conditions must be met before the job can run. It also contains any parameters that the app must pass to the JobService. A JobInfo object is not directly instantiated, instead it is created by using a JobInfo.Builder.

Methods
A JobService sub-class must override two methods:

OnStartJob: A system invokes when the job starts and runs on the main thread of the app.

If the work is a small, easy task (less than 16 milliseconds), it will run on the main thread. Lengthy tasks such as disk access or network calls must run asynchronously. OnStartJob should return "true" if it is running work on another thread, while "false" should be returned if the all the work was performed within OnStartJob itself.

 OnStopJob: Called when the system has to prematurely terminate the job and provide the JobService a chance to perform any necessary cleanup. If the job should be rescheduled, it will return "true".
 
Applying JobScheduler
The following code shows a sample JobService type:

	[Service(Name = "JobScheduleSample.FibonacciJob", Permission = "android.permission.BIND_JOB_SERVICE")]
	public class FibonacciJob : JobService
	{
	   public override bool OnStartJob(JobParameters jobParams)
	   {
	      // Called by the operating system when starting the service.
	      // Start up a thread, do work on the thread.
	      return true;
	   }
	   public override bool OnStopJob(JobParameters jobParams)
	   {
	      // Called by Android when it has to terminate a running service.
	      return false; // Don't reschedule the job.
	   }
	}
	
Create a JobInfo Object

In order to schedule a job, it’s necessary for an app to use a JobInfo.JobBuilder to create a JobInfo object. The JobInfo.JobBuilder has a fluent interface and is used to collect meta-data, such as the type of JobService to instantiate and any conditions that should be met before the job is run. This snippet shows how to create a JobInfo class to run the FibonacciJob (from the example above), but only when the device is connected to an “unmetered” (free) network. The job should run between one and five seconds from being scheduled:
 

	Java.Lang.Class javaClass = Java.Lang.Class.FromType(typeof(FibonacciJob);
	ComponentName component = new ComponentName(context, javaClass);
	JobInfo.Builder builder = new JobInfo.Builder(context, component)
					     .SetMinimumLatency(1000)   // Wait at least 1 second
					     .SetOverrideDeadline(5000) // But no longer than 5 seconds
					     .SetRequiredNetworkType(NetworkType.Unmetered);
	JobInfo jobInfo = builder.Build();

In the previous example, the context is any Android Context, such as an Activity. The parameter is a unique integer that identifies the job service to the JobScheduler.
 

JobFinished
Finally, when a JobService has finished its work (regardless of which thread the work is running on), it should call its own JobFinished() method. It’s important to call this method because it tells the JobScheduler that the work is done and it’s safe to release any wake locks that were acquired for the JobService in the first place. This diagram illustrates how the JobService methods relate to each other and how they would be used:

Wrapping Up
Now that you’ve seen the basics of the JobScheduler API.Android application to replace a task done in a background service. This is a great opportunity to enhance the experience your user has with your applications andupdate to Android Oreo 8.0 all at once! You can find a simple sample on GitHub that shows the JobScheduler API in action. The sample calculates a Fibonacci number in a job and then passes that number back to an Activity.




### What is ADB?
Android Debug Bridge (adb) is a versatile command-line tool that lets you communicate with a device. The adb command facilitates a variety of device actions, such as installing and debugging apps, and it provides access to a Unix shell that you can use to run a variety of commands on a device

### What is ANR?
What is AndroidManifest.xml used for? Give examples of what kind of data you would add to it. [info]
Describe how broadcasts and intents work to be able to pass messages around your app.[info]
What is the Dalvik Virtual Machine?
What are different ways to store data in your Android app? [info]
different data storage options available on Android:

### Internal file storage: Store app-private files on the device file system.
External file storage: Store files on the shared external file system. This is usually for shared user files, such as photos.
Shared preferences: Store private primitive data in key-value pairs.
Databases: Store structured data in a private database
Android appplication components [info]
What is the relationship between the life cycle of an AsyncTask and an Activity? What problems can this result in? How can these problems be avoided?

An AsyncTask is not tied to the life cycle of the Activity that contains it. So, for example, if you start an AsyncTask inside an Activity and the user rotates the device, the Activity will be destroyed (and a new Activity instance will be created) but the AsyncTask will not die but instead goes on living until it completes.

Then, when the AsyncTask does complete, rather than updating the UI of the new Activity, it updates the former instance of the Activity (i.e., the one in which it was created but that is not displayed anymore!). This can lead to an Exception (of the type java.lang.IllegalArgumentException: View not attached to window manager if you use, for instance, findViewById to retrieve a view inside the Activity).

There’s also the potential for this to result in a memory leak since the AsyncTask maintains a reference to the Activty, which prevents the Activity from being garbage collected as long as the AsyncTask remains alive.

For these reasons, using AsyncTasks for long-running background tasks is generally a bad idea . Rather, for long-running background tasks, a different mechanism (such as a service) should be employed.


### What is dependency injection?
### What are the different protection levels in permission?
### How would you preserve Activity state during a screen rotation?

You need to override onSaveInstanceState(Bundle savedInstanceState) and write the application state values you want to change to the Bundle parameter like this:

	@Override
	public void onSaveInstanceState(Bundle savedInstanceState) {
	  super.onSaveInstanceState(savedInstanceState);
	  // Save UI state changes to the savedInstanceState.
	  // This bundle will be passed to onCreate if the process is
	  // killed and restarted.
	  savedInstanceState.putBoolean("MyBoolean", true);
	  savedInstanceState.putDouble("myDouble", 1.9);
	  savedInstanceState.putInt("MyInt", 1);
	  savedInstanceState.putString("MyString", "Welcome back to Android");
	  // etc.
	}

The Bundle is essentially a way of storing a NVP ("Name-Value Pair") map, and it will get passed in to onCreate() and also onRestoreInstanceState() where you'd extract the values like this:

	@Override
	public void onRestoreInstanceState(Bundle savedInstanceState) {
	  super.onRestoreInstanceState(savedInstanceState);
	  // Restore UI state from the savedInstanceState.
	  // This bundle has also been passed to onCreate.
	  boolean myBoolean = savedInstanceState.getBoolean("MyBoolean");
	  double myDouble = savedInstanceState.getDouble("myDouble");
	  int myInt = savedInstanceState.getInt("MyInt");
	  String myString = savedInstanceState.getString("MyString");
	}
	
You would usually use this technique to store instance values for your application (selections, unsaved text, etc.).

### What is View Group in Android?
### What is the difference between view and fragment ? 



A ViewGroup is a special view that can contain other views (called children.) The view group is the base class for layouts and views containers. This class also defines the ViewGroup.LayoutParams class which serves as the base class for layouts parameters.

View class represents the basic building block for user interface components. A View occupies a rectangular area on the screen and is responsible for drawing and event handling. View is the base class for widgets, which are used to create interactive UI components (buttons, text fields, etc.).

### Android Design and XML
### Explain the differences and similarities of Relative Layout and Linear Layout.
### Explain the differences and similarities of List Views and Grid Views.
### Describe how to implement XML namespaces.
### Explain how to present different styles/drawables for a button depending on the state of the button (pressed, selected, etc.) using XML (no Java)
for layout_width and layout_height, what's the difference between match_parent and wrap_content?
### How do you implement Google's new Material Design in an Android application?
### Difference between View.GONE and View.INVISIBLE?

Android Networking
### Have you use an HTTP Library, which, why, did you like it?
### Describe how REST APIs work.
### What are some typical methods of HTTP request/responses? [GET, POST, PUT, PATCH, DELETE, UPDATE]
Databases
### Why does Android use SQLite?
### What libraries have you used for interacting with databases and why did you choose them?
### What are contract classes?
### How do you use the BaseColumns interface to describe your data schema?


## Common Running Time
There are some common running times when analyzing an algorithm:
O(n): Time Complexity of a loop is considered as O(n) if the loop variables is incremented / decremented by a constant amount. For example following functions have O(n) time complexity.

	// Here c is a positive integer constant   
	for (int i = 1; i <= n; i += c) {  
	    // some O(1) expressions
	}

	for (int i = n; i > 0; i -= c) {
	    // some O(1) expressions
	}

O(n^c): Time complexity of nested loops is equal to the number of times the innermost statement is executed. For example the following sample loops have O(n^2) time complexity

	for (int i = 1; i <=n; i += c) {
	   for (int j = 1; j <=n; j += c) {
	      // some O(1) expressions
	   }
	}

	for (int i = n; i > 0; i += c) {
	   for (int j = i+1; j <=n; j += c) {
	      // some O(1) expressions
	}
	
For example Selection sort and Insertion Sort have O(n^2) time complexity.
O(Logn) Time Complexity of a loop is considered as O(Logn) if the loop variables is divided / multiplied by a constant amount.

	for (int i = 1; i <=n; i *= c) {
	   // some O(1) expressions
	}
	for (int i = n; i > 0; i /= c) {
	   // some O(1) expressions
	}
	For example Binary Search has O(Logn) time complexity.

O(LogLogn) Time Complexity of a loop is considered as O(LogLogn) if the loop variables is reduced / increased exponentially by a constant amount.

	// Here c is a constant greater than 1   
	for (int i = 2; i <=n; i = pow(i, c)) { 
	   // some O(1) expressions
	}
	//Here fun is sqrt or cuberoot or any other constant root
	for (int i = n; i > 0; i = fun(i)) { 
	   // some O(1) expressions
	}
	
One example of time complexity analysis

	int fun(int n)
	{    
	    for (int i = 1; i <= n; i++)
	    {
		for (int j = 1; j < n; j += i)
		{
		    // Some O(1) task
		}
	    }    
	}

	Analysis:


	For i = 1, the inner loop is executed n times.
	For i = 2, the inner loop is executed approximately n/2 times.
	For i = 3, the inner loop is executed approximately n/3 times.
	For i = 4, the inner loop is executed approximately n/4 times.
	…………………………………………………….
	For i = n, the inner loop is executed approximately n/n times.

So the total time complexity of the above algorithm is (n + n/2 + n/3 + … + n/n), Which becomes n * (1/1 + 1/2 + 1/3 + … + 1/n)
The important thing about series (1/1 + 1/2 + 1/3 + … + 1/n) is equal to O(Logn). So the time complexity of the above code is O(nLogn).


http://discrete.gr/complexity/




