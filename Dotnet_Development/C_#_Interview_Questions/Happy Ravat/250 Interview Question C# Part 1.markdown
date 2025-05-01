# OOPS & C#
## (Basics)
### Q1 : What is C# ? What is the Difference between C# and .NET ? (1)
Ans :  C# ek programming language hai . Isse Microsoft na banaya hai Iska use hum software , websites, apps banane ke liya karta hai 

.NET ek platform/framework hai. ye ek aisi jagah hai jahan C# code run hota hai. .NET me bahut saari cheezein hoti hain — jaise tools, libraries, and environment — jo coding aur software banane ke kaam aati hain.

Ek chhoti analogy (example):
Socho tum ek chai bana rahe ho ☕:

C# = Recipe (kaise banani hai chai)

.NET = Kitchen (jahan chai banegi, sab tools bhi wahi hain)

### Q2 : What is OOPs ? What are the main concepts of OOPs(2)
Ans : OOPs ka full form hota hai: Object-Oriented Programming System.
Ye ek tariqa (style) hai code likhne ka, jahan hum real-life cheezon ko software mein objects ke form mein represent karte hain.
Simple words mein:
Jaise real life mein sab kuch objects hote hain — car, mobile, insaan — waise hi programming mein bhi hum har cheez ko object bana ke kaam karte hain.

Main Concepts of OOPs 
1. Encapsulation – (Data ko box mein band karna)
2. Inheritance – (Baap se beta sikhta hai)
3. Polymorphism – (Ek kaam, alag-alag tareeke se)
4. Abstraction – (Sirf kaam ka part dikhana, baaki chhupana)

### Q3 : Advantage Of OOPs?
Ans : Advantages :
1. Code Reusability : Ek baar class banao, baar-baar use karo (thanks to inheritance).
2. Data Security : Data encapsulation se sensitive data chhup jata hai, direct access nahi milta.
3. Easy to Maintain : Code alag-alag parts (classes) mein hota hai, isliye changes karna easy hota hai.
4. Flexibility & Modularity : Har class apna kaam karti hai — modular code = clean code.

### Q4 : Limitations of OOPs
Ans : Problems
1. Thoda Complex for Beginners : Concept samajhne mein time lagta hai — class, object, inheritance sab ek saath samajhna padta hai.
2. Zyada Memory Use : Object creation aur abstraction ke chakkar mein normal programming se thoda zyada resources lagte hain.
3. Slow Execution : Kabhi-kabhi abstraction & polymorphism ki wajah se speed slow ho sakti hai (compared to functional programming).
4. Over Design ka Risk : Chhoti problems ke liye bhi agar unnecessary classes banaye, to code heavy ho jata hai.

### Q5 : What are Classes and Objects ?
Ans : Class : Design / Blue print hoti hai.  "Car"
      Objects : Us class ka real version (jo memory ma banta ha) . "Meri Alto Car"

### Q6 : What are the tyes of classes in C# ?
Ans : 
1. Static Class : sirf static members , objects nahi banta .
2. Abstract Class : Direct Object Nahi banta , but inherit krna ka liya.
3. Sealed Class : IS Ko koi Inherit nahi kr skta .
4. Partial Class : Ek hi class ko alag alag file ma likhna
5. Normal Class – Regular class, jisme object banta hai.

### Q7 : Is it possible to prevent object creation of a class in C#?
Ans : Yes , By Using Abstract Class , Private Class , Static Class.

### Q8 : What is a Property?
Ans : Property = Bridge between private variable and Pulic access.
      Get/Set ke throught value lete ya dete hai
      property implements the princile of encapsulaton.
        public string Name {get; set;}

### Q9 : What is difference Between PRoperty and Function?
Ans : Property	                        Function
      Value ko get/set karta hai	    Kaam perform karta hai
      Syntax short & clean hota hai	    Function ke andar logic hota hai
      Usually get/set ke liye hota	    Task ya action perform karta hai
🧠 Property = "Name"
🧠 Function = "PrintName()"


### Q10 : What are Name Spaces ?
Ans : Namespace  Folder jaisa kam karta ha jisme classes, functions group hote hain.
Ye naming conflicts se bachata hai.

## (Inheritance ,Polymorhism, Excapsulation ,Abstarction)

### Q11 : What is Inheritance ? When to USe Inheritance ?
Ans : inheritance : Ek Class(child) doosri class (parent)ke features use kare. Use karo jab common funcationality ko use krna ho.
Example:
Vehicle class se Car, Bike, Bus inherit kar sakti hai.

### Q12 : What are different types of Inheritance ?
Ans : 
1. Single – One base → one derived
2. Multilevel – Base → Derived1 → Derived2
3. Hierarchical – One base → many derived
4. Hybrid – Combination of above

### Q13 : Does C# Support Multiple Inheritance?
Ans : No – C# does not support multiple inheritance with classes.
      But multiple interfaces can be inherited.

### Q14 : How To prevent a Class from from being Inherited to the derived class ?
Ans : Use sealed keyword:
```c#
sealed class MyClass { }
```

### Q15 : Are private class members Inherited to the Derived class ?
Ans : No – private members inherit hote hain but directly accessible nahi hote.
Child class unhe use nahi kar sakta directly.

### Q16 : What is Abstraction ?How To Implement Abstraction?
Ans : Abstraction = sirf important info dikhana, details chhupana.
C# mein implement karo:

### Q17 : What is Excapsulation ? How to implement encapsulation ?
Ans : Encapsulation = data ko class ke andar hi rakhna (wrap karna).
Implement by:
1. Private variables
2. Public properties (get/set)

```c#
private int age;
public int Age { get; set; }
```


### Q18 : What is Difference between Abstartion and Encapsulation?
Ans :   Abstraction	                            Encapsulation
        Focus on what to show	                Focus on how to protect
        Hides complex logic	                    Hides internal data
        Achieved via abstract class/interface	Achieved via properties & access modifiers

### Q19 : What is Polymorphism and What are its types? When to Use Polymorphism?
Ans : Polymorphism  : Ek Kaam, alag - alag trika se karna.

Types: 
1 Compile Time (Overloading)
2 Run Time (Overriding)

### Q20 : What is Method OverLoading? In How many ways a method can be Overloaded? 
Ans : Same method name, Different parameters.
        Oveloading ho skta hai by : 
        1. Number of parameters
        2. Types of parameters
        3. Order of parameters

```c#
void Print()  
void Print(string name)  
void Print(int age, string name)    
```  

### Q21 : When Should you use method overloading in real applications?
Ans : Use when same action karna hai but input alag-alag ho.
Example:
Log() method → ek baar sirf message log karo, kabhi message + error code.

```c#
Log(string message)  
Log(string message, int code)
```


### Q22 : If two methods have same except return type, then methods are overloaded?
Ans :  No! Only return type alag hone se overloading nahi hoti.
C# confuse ho jata hai kis method ko call karna hai.

### Q23 : What is the difference between Overloading and Overriding?
Ans : 
1. OverLoading :
    Compile Time 
    Same Class ma hota ha
    Parameter Must be Different
    No Specific KeyWord is Needed

2. Overridding
    Run Time
    Clild Class Overrides parent class
    Signature same hota hai
    Use virtual and override.

### Q24 : Use of Overriding ? When should I override the method in real applications ?
Ans : Overriding tab use karte hain jab child class mein behavior change karna ho parent method ka.
Example:

-> Base Account class ka CalculateInterest() method.

-> SavingsAccount ya CurrentAccount us method ko apne tareeke se override karega.

### Q25 : Method is marked as virtual,do we have to "override" it from the child base?
Ans : No, override karna optional hai.
   Agar override nahi karoge to base class ka hi version chalega.     

### Q26 : What is the difference between Method Overriding and Method Hiding?
Ans : Method Overloading : same name, different parameters
      MEthod Overriding : child changes base method behavior
      Method Hiding : child method hides base method using new

Method Overriding :
1. Key Word : override 
2. Base method : Must be vistial or abstract
3. RunTime : Based on object type (dynamic)
4. Use when :Want to change behavior

Method Hiding :
1. Key Word : new
2. Base method : Can be any method
3. RunTime : Based on reference type (static)
4. Use when : Want to hide method from base class

## (Abstract Class and Inheritance)
### Q27 : What is the difference between Astract class and an Interface?
Ans : Abstract Class
        Methods : Can have Body + Abstract methods
        Access Modifiers : Can have public, protected etc.
        Fields/Constructors : Allowed
        Inheritance : Only one abstract class inherit allowed

      Interface : 
        Methods : C# 8+ mein default body allowed
        Access Modifiers : Methods are pulic by default
        Fields/ Constructors : Not Allowed
        Inheritance : Multiple Interfaces allowed.

### Q28 : When to use Interface and When Abstract class in real applications?
Ans : Use Interface :   
        - Jab multipe inheritance chahiye.
        - Jab only method structure define karna ho (contract - type)
      
      Use Abstract Class :
        - Jab partially common logic + Partially customer logic chahiya.
        - Jab kuch default implementation dena ho

### Q29 : Why to create interfaces in real applications?
Ans : 
1. Loose coupling (dependency injection jaisa kaam)
2. Easy testing (mocking)
3. Clean architecture
4. Reusability aur flexibility

Service layer uses IMailSerice -> Real app main GmailService , test mein FakeMailService.

### Q30 : Can We define body of Interface methods? When To define methods in Interfaces?
Ans : In C# 8+ Yes We can Using default keyword.
      In Normally No.

### Q31 : Can you create an instance of Abstract class and Interface?
Ans : No , We can Directly 
        But can make a reference using Derived class.

### Q32 : Do Interface can have a Construnctors in C#?
Ans : No – constructors nahi hote.
        Because interface ka object kabhi banta hi nahi.

### Q33 : Can abstract class have Constructors?
Ans :  Yes!
        Constructor bana sakte ho – child class ke object creation ke time wo call hota hai.

### Q34 : What is the difference between Abstraction and Astract class?
Ans : Abstraction
        - Concept of hiding details
        - Achieved via abstract class or interface
        - Theory Level

      Abstract Class(Implementation)
        - One way to implement abstraction
        - It's a class used to implement abstraction
        - Pratical syntax - level 

### Q35 : Can Abstract class be sealed or static in C#?
Ans :  No – abstract ka matlab "extend karo",
        sealed ka matlab "extend mat karo",
        Dono ek saath conflict mein hain.
        also, static bhi ❌ nahi chalega with abstract.

### Q36 : Can you declare abstract methods as private in C#?
Ans : No – abstract methods must be public or protected
        Because private method inherit hoke bhi use nahi ho sakta.

### Q37 : Does Abstract class suppport multiple Inheritance?
Ans : No – abstract class bhi ek hi base class inherit kar sakta hai.
        But ✅ multiple interfaces implement kar sakte ho.

## (Access Specifiers, Boxing , Unboxing , String And String Builder)
### Q38 : What are Access Speficiers?
Ans : 
    public              har jagha access
    private             Sirf usi class ka andar
    protected           Sirf usi class + uski derived classes
    internal	        Same assembly ke andar
    protected internal  Derived classes + same assembly
    private protected	Derived classes within same assembly

### Q39 : What is internal modifier? Show Example.
Ans : internal = member ya class sirf same project/assembly ke andar accessible hoti hai.

### Q40 : What is default Access modifier in a class?
Ans : Top-level class → internal by default
      Class members → private by default

### Q41 : What is Boxing and Unbxing? Where to use Boxing and Unboxing in real applications?
Ans : Boxing = Value type -> reference type (int to object)
      Unboxing = reference type -> value type(object to int)

        ```c#
        int num = 10;
        object obj = num;           // Boxing
        int again = (int)obj;       // Unboxing

        ```
        Real Use: Jab old collections (like ArrayList) use karte ho jo object type store karte hain.

### Q42 : Which one is Explicit Boxing or Unboxing?
Ans : Boxing → Implicit , Unboxing → Explicit (typecast lagta hai)

### Q43 : Is Boxing and Unboxing Good for PErformance?
Ans : No – ye slow hai because
      Boxing ➕ Unboxing = extra memory copy
      Use generics instead for better performance

### Q44 : What are the basic string operations in C#?
Ans :   Length, ToUpper(), ToLower()
        Substring(), Replace(), IndexOf()
        Split(), Trim(), Concat()
        Equals(), Compare()

### Q45 : What is the Difference between "String" And "StringBuilder"?
Ans :  
1. String are immutable , while stringbuilder are mutable
2. String Create new object on every chnage , Modify the safe in sb
3. Strings are Slower for many edits ,  Faster for multiple string operations

### Q46 : When to use String and When StringBuilder in real Applications?
Ans :   string: jab 1-2 baar modification ho (e.g., simple messages, logs)
        StringBuilder: jab loop mein baar baar string modify karni ho

### Q47 : What is String Interpolation in c#?
Ans : Ek easy way to insert variables inside string
      Use $ sign

## (Loops, Conditions, Exception Handling)
### Q48 : What are the loop types in C# ? When to use what in real applicationS?
Ans : for - Ja Fixed iteratons ho  (eg loop fro 1 to 100)
      while - Jab condition pe depend karta ho (unknown repeat)
      do-while - Jab pehle ek baar run zaroor karna ho
      foreach - Jab collections/lists par iterate karna ho

### Q49 : What is the difference between "Continue" and "break" statement?
Ans : break : Loop turant chhod deta hai
      continue	Current iteration skip, next pe jump

### Q50 : What are the alternative ways of writing if -else  conditions? When to use What?
Ans : Ternary operator	Simple one-line condition
      Switch statement	Multiple values to check
      Null-coalescing	Null checks (??)

### Q51 : How to implement Exception Handling in C#?
Ans : Use try-catch-finally

### Q52 : Can we exceute mltiple Catch blocks ?
Ans : Yes! Multiple catch blocks chalte hain based on exception type.

### Q53 : When to use finally in real application?
Ans : Jab kuch bhi cleanup/closing ka kaam ho – chahe error aaye ya na aaye:
        File close
        DB connection close
        Release resources

### Q54 : Can we have only "Try" block without "Catch" block in real applicaitonS?
Ans :  Yes – but tab finally hona chahiye.

### Q55 : What is difference between Finally and Finalize ?
Ans : finally	Cleanup block – manual, in code
      Finalize	Destructor – automatic, by garbage collector

### Q56 : What is the difference between "throw ex" and "throw" ? Which one to use in real applicatipn?
Ans : throw ex	Resets stack trace (not recommended)
      throw	Preserves original error details (✅ Recommended) 
      
## (Generics & Collections)
### Q57 : Explain Generics in C#? When and Why to Use?
Ans : Genric means type safe templates.
      Aap ek hi class / method likh ke multiple data type ke saath use kr skte ho

      Why Use?
      - Type safety(Noboxing /unboxing)
      - Better perfornmace
      - Reuable code

      When ?
      - jab aapko collection banani ho specific type ke liya.
      - Cutom genric methods/ classes likhe ho


### Q58 : What are Collections in C# and What are their Types?
Ans : Collection : group of objects ko handle karne ka way.
    Type : Non-Generic (OLD) : ArrayList, Hashtable ,stack, queue
           Generic : List<T>,Dictionary<TKey,TValue>,Queue<T>,HashSet<T>

### Q59 : What is difference between Array and ArrayList?
Ans :  Feature     Array     ArrayList
       Type-Safe   Yes       No (Stores Object)
       Size        Fixed     Dynamic
       Performace  Faster    Slower(Due to boxing / Unboxing)
       Use Case    Simple    Old Dot.NET

### Q60 : What is difference between ArrayList and Hastable?
Ans : Feature	    ArrayList	                    Hashtable
      Store Type	List of values (index-based)	Key-value pair
      Access	    Index based	                    Key based
      Example	    arrayList[0]	                hash["name"]

### Q61 : What is the difference between List and Dictionary Collections?
Ans : Feature	List<T>	                Dictionary<TKey, TValue>  
      Type	    Collection of values	Collection of key-value pairs
      Access	By index	            By key
      Use Case	Ordered list	        Fast lookup via key

### Q62 : What is IEnumerable in C#?
Ans : Interface jo loop lagane(foreach) ke liya support deta hai
      ```c#
      IEnumerable<int> nums = new List<int>() { 1, 2, 3 };
      ```
      - Lazy execution
      - Read only excess
      - Common return type for LINQ queries

### Q63 : What is difference Between IEnumerable and IEnumerator in C#?
Ans : IEnumerable 
        1. Purpose           Collection Ko Represent krta ha
        2. Method            GetEnumerator()
        3. Use               foreach loop

      IEnumerator
        1. Purpose           One-by-one iteration control karta hai
        2. Method            MoveNext(), Current, Reset()
        3. Use               Custom manual loop


### Q64 : What is the difference between IEumnerable and IQueryable in C#? Why to use IQueryable in sql queires?
Ans : IEnumerable 
        1. Exceution : In - Memory (After DB fetch)
        2. Performace : Slower for large DB data
        3. Use : In-memory collections (Lists)

      IQueryable 
        1. Exceution : Query executes in DB (lazy)
        2. Performace :  Fast for DB filters
        3. Use : Database queries (LINQ to SQL, EF)

    Why Use IQuerable inDB Queries?
    - Filters are converted to SQL
    - Only required data fetched -> Better performance 

## (Constructors)
### Q65 : What is Constructor? When to use constructor in real applications?
Ans : Constructor ek special method hota hai jo class ka object create karte hi auto call hota hai.
Use in real life:
- Object ko default ya specific value dena
- Dependency inject karna
- Initial setup karna

### Q66 : What are the types of constructors? 
Ans : Default , Parameterized , Copy , Static , Private

### Q67 :  What is Default Constructor?
Ans : Constructor with no parameters. Agar tum nahi likhte, to compiler khud bana deta hai.

### Q68 : What is Parameterized constructor?
Ans : Constructor jo values accept karta hai during object creation.
 
### Q69 : What is Static constructor ? What is the use in real applications?
Ans : Static constructor class ke first time use hone pe auto call hota hai (only once).
- Static variables ko initialize karna
- External config/load karna

### Q70 : Can we have parameters or access modifier in static constructor?
Ans : No 
- No parameters 
- No Access modidiers (always private implicitly)

### Q71 : What is a Copy Construtor?
Ans : Constructor jo ek existing object ki copy banata hai. ,Manual likhna padta hai, C# doesn’t auto-generate.

### Q72 : What is Private constructors? What is the use  ?
Ans : Constructor jo only class ke andar accessible ho.,To prevent object creation from outside (Singleton pattern, static classes)

### Q73 : What is Constructor Overloading?
Ans : Jab ek hi class mein multiple constructors ho different parameters ke saath.

### Q74 : What is Destructor ?
Ans : Destructor (~ClassName()) object destroy hone pe call hota hai. Rarely used in C#.

### Q75 : Can We Create object of class with private constructor in C#?
Ans : No (from outside class) , But class ke andar se object banaya jaa sakta hai. Example : Singleton pattern ke liye perfect use case.

### Q76 : If base class and child class both have constructor which one will be called first, When derived class object is Created ?
Ans : Base class constructor runs first, phir derived class ka.

## (Methods , Parameters, Delegates & Events)
### Q77 : What is a Method in C#?
Ans : Method = block of code jo specific task perform karta hai.
Reusability ke liye methods use hote hain.

### Q78 : What is difference between Pass By Value and Pass By Reference
Ans : 
- Pass By Value Default in C# , Pass By reference is not.
- Pass By Value Dont change Original Data , Pass By Reference Do.
- In Pass By Value no keyword Involves , we use ref and out in case of pass by reference.

### Q79 : How To Resturn More Then one Value from a meths in C#?
Ans : 
1. using out Parameter
2. Retur Tuple
3. Return a Custom class

### Q80 : What is Difference between ref and Out?
Ans :
1. Ref Must be initialize before pass ? ,While Out Dont
2. Ref Use for read and write , Out use for Write only
3. Ref use for modify input and Out use for retutn multiple value.s

### Q81 : What is "params" keyword? when to use params keyword in real applications?
Ans :  params allow karta hai variable number of arguments pass karna.
        Kitna bi Valiable pass kr do.
        Use when: method ka argument count fix nahi ho.

### Q82 : What are otional parameters in a method?
Ans : Method parameters jo default value lete hain agar caller provide nahi kare.

### Q83 : What are the named parameters in a method ?
Ans : Method call karte time, parameter name likh ke value pass karna.
        Better readability + koi bhi order mein pass kar sakte ho.

### Q84 : What are Extension methods in C#? When to use extension methods ?
Ans : Method jo existing class ko bina modify kiye new method de deta hai.
Custom utility methods for built-in types like string, DateTime, etc.

### Q85 : What are Delegates in C#? When to use extension methods?
Ans : Delegate = type-safe pointer to a method.
```c#
delegate void MyDelegate(string msg);

void Show(string m) => Console.WriteLine(m);
MyDelegate d = Show;
```
When USe 
1. You want to pass methods as parameters
2. Implement callbacks or events

### Q86 : What are Multicast Delegates in C# ?
Ans : Delegate jo multiple methods ko hold karta hai.
Used in event-driven programming.

### Q87 : What are Anonymous Delegates in C#?
Ans : Delegate without separate method name (inline method).
    Short, one-time use logic — no need to create full method.

### Q88 : What are the Difference between Events and Delegates?
Ans : The Event is a notification mechanism that depends on delegates
        An Event is dependent on a delegate and cannot be crated with delegates.
        Event is like a wraper over the delegate to improve its security.

## (Important Keywords)
### Q89 : What is 'this' Keyword in C# ? When to use it in real applications?
Ans : this refers to current object of the class.
 Use when:
 - Local variable name clashes with class member
 - To pass current object (this) as parameter
 - Inside constructor chaining

### Q90 : What is the purpose of "Using" Keyword in C# ?
Ans : 
1. Namespace include karne ke liye
2. Dispose auto call karne ke liye (for unmanaged resources like DB, file)
```c#
using (SqlConnection con = new SqlConnection(...)) {
   // con.Dispose() auto called
}
```

### Q91 : Can we use Using Keyword with other classes apart from DBConnection?
Ans :  Yes
Any class that implements IDisposable can be used with using.
ExampleS: FileStream , StreamReader, HttpClient 

### Q92 : What is the difference between "is" and "as" operators?
Ans : 
Feature	    is	                         as
Type check	✅ Yes	                    No (direct cast)
Returns	    true/false	                  object or null
Use case	Before typecasting safely	  Cast without exception

### Q93 : What is the difference between "Readonly" and "Constant" variable?
Ans : 
- ReadOnly Set At Runtime ,Constant Sets at Complie Time
- ReadOnly Can change Once during object creation , const cannot change once created 
- realonly is not static , const is always static

### Q94 : What is "Static" class ? When to use static classs in real application?
Ans : Class that cannot be inherited and All members must be static.
        Use When
         - Utility/helper class banana ho (ex: Math, Logger)

    ```c#
    static class MathHelper {
    public static int Add(int x, int y) => x + y;
    } 
    ```   

### Q95 : What is the difference between "var" and "dynamic" in C#?
Ans : 
- var type known at Compile time and dynamic type is known at Runtime.
- var is type safe and dynamic has risk of run time errors.
- Use var when type is clear and dynamic when working with unknown types (like JSON , COM , etc)

### Q96 : What is Enum Keyword use for?
Ans : Used to define named constants. Makes code clean & readable.
Use when : Set of related fixed values .(Exchnage codes)


### Q97 : Is it possible to inherit Enum in C#?
Ans : Enums can't be inherited because they are value types (sealed by default).

### Q98 : What is the use of Yield Keyword in C#?
Ans : yield allows you to return values one by one (lazy evaluation) from a method that returns IEnumerable.

```c#
IEnumerable<int> GetEven() {
    for (int i = 0; i < 10; i += 2)
        yield return i;
}
```
Use when 
- You want better memory performace
- Return values as needed (especially for large collections)

## (LINQ)
### Q99 : What is LINQ ? When to use LINQ in real appliations?
Ans : LINQ (Language Integrated Query): C# ka feature jo allow karta hai data ko query karna jaise SQL — but directly within C# code.

Use When 
- Lists, arrays, database, XML ko filter/sort/transform karna ho
- Code ko short aur readable banana ho

### Q100 : What are the advantage and disadvatages of LINQ?
Ans : 
Advantages:
- Easy to write (SQL-style syntax)
- IntelliSense support
- Type-safe (compile-time errors milte hain)
- Works with different data sources (List, DB, XML, etc.)

Disadvantages :
- Performance low for complex queries (vs stored procedures)
- Hard to debug for big queries
- Sometimes not flexible for advanced DB queries

### Q101 : What is Lambda Expressions ? What is the use i real applications?
Ans :Lambda = Short function without name
USed With LINQ , delegates, events
Real Use : Filter list items, Pass logic in methods ,Work with LINQ & Delegates

### Q102 : What is the difference between First and FirstorDefault method
Ans : First : First matching item, throws expetion if not found
      FirstorDefault : First matching item or null/default ,No (returns null or default)


## (More Questions)
### Q103 : What is the differece between a class and structure?
Ans : Class : Reference type , stored in heap , support inheritance
      Structure (struct) : Value type , stored in stack , lightweight , no inheritance

      Use Class : When Complex behaviour needed
      Use struct : Lightweight , small data

### Q104 : What is Operator Over Loading?
Ans : C# me operator ka meaning chnage karna for custom objects.
        public static MyClass operator +(MyClass a, MyClass b) { ... }

### Q105 : CAN YOU CALL THE BASE CLASS METHOD WITHOUT CREATING AN INSTANCE? 
Ans : Yes if the class is static.

### Q106 : WHAT ARE VIRTUAL FUNCTIONS AND PURE VIRTUAL FUNCTIONS? 
Ans : Virtual : Base class me defined hota hai, Child class ma override kar skta hai.
Pure Virtual : C# me nahi hota, ya C++ ma hota ha .C# ma abstract ka use hota ha for similar behaviour.

### Q107 : WHICH OOPS CONCEPT EXPOSES ONLY THE NECESSARY INFORMATION TO THE CALLING FUNCTIONS?
Ans :  Encapsulation

### Q108 : IS It necessary to create bjects from class?
Ans : Nahi. Agar class me static members hain, toh direct use kar sakte ho — bina object banaye.

### Q109 : What is Early And Late Binding?
Ans : Early Binding (Compile Time) : Method known at compile time.
        Late Binding(Run - Time) : Method resolved at runtime(like dynamic, reflection, interfaces).

### Q110 : WHICH OOPS CONCEPT IS USED AS A REUSE MECHANISM? 
Ans : Inheritance

### Q111 : IN TRY BLOCK IF WE ADD RETURN STATEMENT WHETHER FINALLY BLOCK IS EXECUTED? 
Ans :  Yes , Finally block will still be executed in presence of return statement in try block.

### Q112 : What you mean by inner exception?
Ans : Ek exception ke andar doosra exception — jisse exact root cause trace kar sakte hain.

### Q113 : List Out Some of the exceptions?
Ans :NullReferenceException , IndexOutOfRangeException , DivideByZeroException , InvalidCastException , FileNotFoundException

### Q114 : What are the difference between stack and queue collections?
Ans : Stack : Last In , first out (Push() , Pop())
        Queue : First In, First out (Enqueue() , Dequeue())

### Q115 : Explain Jagged Arrays?
Ans : Array of arrays — har inner array ki length alag ho sakti hai

```c#
int[][] jagged = new int[2][];
jagged[0] = new int[3];
jagged[1] = new int[5];
```

### Q116 : Explain Multidimensional Arrays? 
Ans : Matrix type arrays - fixed rows and columns.

```c#
int[,] matrix = new int[2, 3];
```

### Q117 : Explain Indexers?
Ans : Custom way to access class data using index like array:

### Q118 : WHAT IS THE DIFFERENCE BETWEEN METHODS – “SYSTEM.ARRAY.CLONE()” AND “SYSTEM.ARRAY.COPYTO()”? 
Ans : Clone() – Creates shallow copy (returns object)
      CopyTo() – Copies to existing array

### Q119 : What are Value Type and Reference Types?
Ans : Value Type: Stack, holds data directly (int, bool, struct)
      Reference Type: Heap, holds address (class, string, array)

### Q120 : CAN WE OVERRIDE PRIVATE VIRTUAL METHOD? 
Ans : No, private method cannot be virtual or overridden.

### Q121 : Explain Circular Reference?
Ans : 2 objects referencing each other — garbage collector can’t clean them easily

### Q122 : Explain Object Pool?
Ans : Pre-create and reuse objects instead of creating new each time — performance improve hota hai (used in DB or connection-heavy apps)

### Q122 : What are the types of Delegates?
Ans : Single-cast delegate
Multi-cast delegate
Anonymous delegate
Generic delegate (Func, Action, Predicate)

### Q123 : WHAT ARE THE THREE TYPES OF GENERIC DELEGATES? 
Ans : 
Func<> - Return Value
Action<> - return Void
Predicate<> - Returns bools

### Q124 : WHAT ARE THE USES OF DELEGATES?
Ans :
Call methods dynamically
Event handling (e.g., Button Click)
Callbacks, notifications
Loose coupling between components

### Q125 : CAN WE USE DELEGATES FOR ASYNCHRONOUS METHOD CALLS? 
Ans : Haan, delegates ko async call kar sakte ho using BeginInvoke() and EndInvoke()
But ab async/await preferred hai.

### Q126 : WHAT IS AN ESCAPE SEQUENCE? NAME SOME STRING ESCAPE SEQUENCES IN C#.
Ans : Special characters inside string, starts with \
\n – New line
\t – Tab
\\ – Backslash
\" – Double quote

### Q127 : WHAT ARE REGULAR EXPRESSIONS? 
Ans : Pattern matching syntax for strings .Use in: Validation (email, mobile number), search/replace

### Q128 : WHY TO USE LOCK STATEMENT?
Ans : To prevent multiple threads from accessing same code block at the same time — thread safety

### Q129 : WHAT IS “EXTERN” KEYWORD? 
Ans : Tells C# method is implemented externally (like in C/C++ DLL)
```c#
[DllImport("user32.dll")]
public static extern int MessageBox(...);
```

### Q130 : WHAT IS “SIZEOF” OPERATOR?
Ans : Returns size (in bytes) of value types (works in unsafe context)

### Q131 :  CAN WE USE “THIS” INSIDE A STATIC METHOD? 
Ans : No, because this refers to current object — and static method has no instance.

### Q132 : WHAT IS THE DIFFERENCE BETWEEN CTYPE AND DIRECTCAST? 
Ans : C# me mainly as or (Type)

### Q133 : WHICH STRING METHOD IS USED FOR CONCATENATION OF TWO STRINGS? 
Ans : String.Concat(str1, str2)

### Q134 : WHAT IS PARSING? HOW TO PARSE A DATE TIME STRING? 
Ans : Converting string to actual data type
```c#
DateTime dt = DateTime.Parse("2025-04-05");
```
Use TryParse() to avoid exceptions.

### Q135 : Explain Partial Class? 
Ans : Split one class in multiple files using partial keyword.
Auto-generated code (like WinForms)
Team work on large class

### Q136 : EXPLAIN ANONYMOUS TYPE? 
Ans : Object without defining a class — used in LINQ mostly

### Q137 : EXPLAIN GET AND SET ACCESSOR PROPERTIES? 
Ans : Used in properties for data encapsulation

### Q138 : WHAT IS COVARIANCE IN C#? 
Ans  : Allows derived class object to be assigned to base class reference in generics or delegates 