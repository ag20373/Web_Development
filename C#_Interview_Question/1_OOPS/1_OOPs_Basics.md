# Part 1 OOPS And C# Basics
## Q1 : What is C#? What is the difference between C# and .NET?
- C# Defination
-- C# (C-Sharp) ek programming language hai
-- jiska use software / applications banane ke liye hota hai.
-- Ex : Mobile apps , Desktop software , Web applications

- .NET Defination
-- .NET ek framework / platform hai
-- jo C# program ko chalane aur support karne ka kaam karta hai.

- Interview
“C# ek object-oriented programming language hai jo Microsoft ne develop ki hai.
.NET ek framework hai jo C# applications ko run karne ke liye runtime aur libraries provide karta hai.”
“Jaise English bolne ki language hai aur mobile us language ko use kar ke call karta hai,
waise hi C# language hai aur .NET usko chalane ka platform hai.”

## Q2 : What is OOPS? What are the main concepts of OOPS?
- Defination
-- OOPS ka full form hai – Object Oriented Programming System
-- OOPS ek programming concept hai / Paradime ha Coding ka
-- jisme hum real-world cheezon ko Objects bana ke code likhte hain.
"OOPS ek programming approach hai jisme hum real-world objects ke through program design karte hain."

- Main Concepts of OOPS
1.. Class : Class ek blueprint / design hoti hai. jiske base pe objects bante hain.
2.. Object : Object class ka real instance hota hai
3.. Encapsulation (Data Protection) : Data ko protect karna aur bundle karna
-- ATM Machine 💳
    - Aap sirf Withdraw kar sakte ho
    - Internal process hidden hota hai
4.. Inheritance (Parent–Child Relation) : Ek class dusri class ki properties use kar sakti hai
5.. Polymorphism (One Name, Many Forms) : Same method, different behavior
6.. Abstraction (Hide Complexity) : Sirf important cheez dikhana, details hide karna

- Interview
"OOPS ek programming concept hai jisme code real-world objects ke around design hota hai.
Iske main concepts hain: Class, Object, Encapsulation, Inheritance, Polymorphism aur Abstraction."

## Q3 : What are the advantages of OOPS?
- Real-World Mapping (Easy to Understand) 
"OOPS me hum real-world objects (Car, Student, Account) bana ke code likhte hain,
isliye code samajhna easy hota hai."

- Code Reusability (Reuse Code)
"Inheritance ki wajah se ek class ka code baar-baar reuse ho sakta hai."

- Better Security (Data Protection)
"Encapsulation ke through hum data ko direct access se protect kar sakte hain."
RealWorld Example : 
-- ATM Machine 💳
    - PIN hidden
    - Sirf withdraw allowed

- Easy Maintenance (Code Manage Karna Easy)
"Agar future me change / bug fix karna ho,
to sirf specific class me change karna padta hai."

- Scalability (Future Growth Easy)
"OOPS me new features add karna easy hota hai
without breaking old code."

- Less Code Duplication
"Common code ko base class me likh dete hain
isliye same code baar-baar likhne ki zarurat nahi."

- Flexibility (Polymorphism)
"Same method name se different behavior milta hai."

- InterView 
"OOPS ke main advantages hain:
Code reusability, better security, easy maintenance, scalability, flexibility aur real-world modeling."

## Q4 : What are the Limitations of OOPS?
- Limitations
1.. Complex Concept (Samajhna Mushkil)
2.. More Memory Usage
3.. Slower Performance
4.. Over Engineering (Extra Design)
5.. Not Good for Small Programs
6.. Requires Proper Planning
7.. Learning Curve Zyada Hai

- Interview
"OOPS ki limitations hain:
Complexity, high memory usage, slower performance, over-engineering aur beginners ke liye learning curve zyada hona." 

## Q5 : What are Classes and Objects?
- Class
-- Class ek blueprint / design hoti hai , jiske base pe objects create hote hain.
-- Class sirf idea hoti hai, real cheez nahi
-- Real Example : 
    Socho Car ka design 🚗
    - Color
    - Speed
    - Engine
-- Ye sirf design hai, car nahi

- Object 
-- Object class ka real instance hota hai , jo memory me actual jagah leta hai.
-- Real Life Example
    - Car ka design → Class
    - Actual car → Object 🚘

- Interview
"Class ek blueprint hoti hai jisme properties aur methods defined hote hain,
aur Object us class ka real instance hota hai jo memory me create hota hai."

## Q6 : What are the types of classes in C#?
- Concrete (Normal) Class
-- Jo class completely implemented hoti hai , aur jiska object create ho sakta hai.
-- Example
class Student
{
    public void Study()
    {
        Console.WriteLine("Student is studying");
    }
}
-- Most commonly used class

- Abstract Class
-- abstract keyword se banti hai
-- Iska object create nahi hota
-- Isme abstract + normal methods dono ho sakte hain
-- Example
abstract class Animal
{
    public abstract void Sound();
}
-- Child class ko method implement karna hi padega

- Sealed Class
-- sealed keyword se banti hai , Isko inherit nahi kar sakte
-- Example
sealed class Bank
{
}
-- Security ke liye use hoti hai



- Static Class
-- static keyword use hota hai
-- Object create nahi hota
-- Saare members static hote hain
-- Example
static class MathHelper
{
    public static int Add(int a, int b)
    {
        return a + b;
    }
}
-- Utility / helper methods ke liye best

- Partial Class
-- Ek class ko multiple files me divide kar sakte hain
-- partial keyword use hota hai
-- Large projects me useful

- Nested Class
-- Ek class ke andar dusri class hoti hai
-- Logical grouping ke liye

- Generic Class
-- Type parameter ke saath banti hai
-- Reusable hoti hai
-- Example
class Box<T>
{
    public T Value;
}
-- Performance + reusability

## Q7 : Is it possible to prevent object creation of a class in C#?
- Yes
-- By Using
1.. By Using Abstract Class
2.. By Using Static Class
3.. By Using Private Constructor ⭐ (Most Asked)

- Interview
"Yes, in C# we can prevent object creation by using abstract classes, static classes, or by making the constructor private."

## Q8 : What is Property?
- Definition
-- "Property ek class member hoti hai , jo class ke private data ko safely access karne ka way deti hai. "
-- Property = Controlled access to variables

- Why Property is Needed?
-- Direct variable (field) ko access karna safe nahi hota ❌
-- Property:
    - Data read / write control karti hai
    - Encapsulation follow karti hai ✔

- Real Example
-- Bank Account 🏦
    - Balance → directly nahi dikhta
    - CheckBalance() → allowed
👉 Property same kaam karti hai

- Auto-Implemented Property (Most Common ⭐)
class Employee
{
    public int Id { get; set; }
    public string Name { get; set; }
}
-- 👉 Internally private variable ban jata hai

- Interview Ready Answer (Short)
"Property C# me ek class member hoti hai jo private variables ko controlled aur secure access provide karti hai using get and set."

## Q9 : What is the difference between Property and Function?
- Property
-- Property data ko access karne ka safe way hoti hai (get / set ke through).
-- Property ka use value read/write karne ke liye hota hai.
Example : 
class Student
{
    public int Marks { get; set; }
}

- Function
-- Function koi kaam / action perform karti hai.
-- Function ka use logic execute karne ke liye hota hai.
-- Example
class Student
{
    public void Study()
    {
        Console.WriteLine("Student is studying");
    }
}

## Q10 : What are Namespaces?
- Defination
-- Namespace ek container / folder hota hai
-- jo classes, interfaces, structs, enums ko organize karne ke kaam aata hai.
-- Namespace ka use name conflict avoid karne aur code ko clean rakhne ke liye hota hai.

- Real Life Example
Socho School 🏫
    -- School
        ---Class10
            ----Student
        ---Class9
            ----Student
👉 Dono ka naam Student hai,
par alag-alag jagah pe hone ki wajah se confusion nahi hota.
School = Namespace

- Why Namespaces are needed
-- Large projects me code organize karne ke liye
-- Same class name ko different jagah use karne ke liye
-- Name conflict avoid karne ke liye
-- Code readable & manageable banane ke liye

- Interview
"Namespace C# me ek logical container hota hai jo classes aur other types ko organize karta hai aur naming conflicts avoid karta hai."

## Q11 : Why Do We need OOPs? 
- OOPS isliye chahiye kyunki ye code ko real-world jaisa, reusable, secure aur easy to manage bana deta hai.

## Q12 : Abstraction vs Encapsulation?
Abstraction
👉 What to show – only essential features, hiding implementation.
👉 Achieved using abstract class / interface.

Encapsulation
👉 How to protect data – wrapping data + methods together.
👉 Achieved using class and access modifiers.

## Q13 : Explain Inheritance ?
👉 Inheritance allows a class to reuse properties and methods of another class.
👉 Achieved using :baseClass keyword in C#.
👉 Supports code reusability. 

## Q14 : Explain virtual keyword ?
👉 virtual keyword allows a method to be overridden in derived class.

## Q15 : What is overriding ?
👉 Overriding means redefining a base class virtual method in derived class.
👉 Uses override keyword.

## Q16 : Explain overloading ?
👉 Overloading means same method name with different parameters.
👉 Happens in the same class.

## Q17 : Overloading vs Overriding ?
Overloading
👉 Same method name, different parameters
👉 Compile-time polymorphism

Overriding
👉 Same method name & signature, different implementation
👉 Runtime polymorphism

# Part 2 OOPS & C# - Inheritance, Abstraction, Encapsulation & Polymorphism
## Q1 : What is Inheritance? When to use Inheritance?
- Defination
-- Inheritance ek OOPS concept hai
-- jisme child class, parent class ki properties aur methods use karti hai.
👉 Matlab Parent → Child relationship

- Real Life Example (BEST)
-- Real Life Example (BEST)
-- Child → Parent ki properties + apni extra qualities
-- Same concept programming me use hota hai.

- Types of Inheritance (Interview Bonus)
-- Single
-- MultiLevel
-- Hierarchical
❌ Multiple inheritance (classes ke saath) C# me allowed nahi
✔ Interface se possible

- When to Use Inheritance?
1.. Inheritance tab use karo jab IS-A relationship ho.
Example 
.. Car is a Vehicle ✔
.. Dog is an Animal ✔
.. Student is a Person ✔
❌ Engine is a Car (Wrong ❌)
...........
2.. When Code Reusability Chahiye
Agar same code multiple classes me repeat ho raha hai to parent class bana ke inherit karo.
...........
3.. When Common Behavior Hai
Example 
.. Start(), Stop()
.. Login(), Logout()
👉 Base class me likho, child me use karo
...........
4.. When Polymorphism Use Karna Ho
Inheritance ke bina polymorphism possible nahi.
Vehicle v = new Car();
v.Start();

- When NOT to Use Inheritance (Important)
1.. Relationship “HAS-A” ho
-- Car has a Engine , 👉 Composition better hai
2.. Sirf Code Reuse ke liye : Wrong design ho sakta hai

- Interview
" Inheritance is an OOPS concept where a child class inherits properties and methods of a parent class.
It should be used when there is an IS-A relationship and code reusability is required. "

## Q2 : What are the different types of Inheritance?
- Types 
1.. Single Inheritance
-- Ek parent class → ek child class
2.. Multilevel Inheritance
-- Grandparent → Parent → Child
3.. Hierarchical Inheritance
-- Ek parent class → multiple child classes
-- Dog Can be Animal , Cat Can be Animal , But not same

## Q3 : Does C# support Multiple Inheritance? How can you implement multiple inheritance in C#?
- Multiple Inheritance (Not Allowed in C#)
-- Ek child class → multiple parent classes
-- C# me classes ke saath allowed nahi
-- Diamond problem avoid karne ke liye

- Multiple Inheritance Using Interface (Allowed)

## Q4 : How to prevent a class from being Inherited?
- 👉 sealed keyword ka use karke hum kisi class ko inherit hone se rok sakte hain.

- Explanation
-- sealed class ko koi bhi dusri class inherit nahi kar sakti
-- Mostly security aur design control ke liye use hota hai

- Can we seal methods also?
-- Code Example
class Parent
{
    public virtual void Show() { }
}
class Child : Parent
{
    public sealed override void Show() { }
}
👉 Ab Show() ko aur koi override nahi kar sakta

## Q5 : Are private class members inherited to the derived class?
- Explanation
👉 No. Private class members are NOT inherited by the derived (child) class.
-- private members sirf usi class ke andar accessible hote hain
-- Child class unko directly access ya use nahi kar sakti
-- Isliye hum kehte hain: private members inherited nahi hote

## Q6 : What is Abstraction? How to implement abstraction in real applications?
- What is Abstraction?
1.. Simple Definition
-- Abstraction ka matlab hai sirf important cheez dikhana aur internal details hide kar dena.
-- User ko kya kaam hota hai dikhate hain
-- User ko kya kaam hota hai dikhate hain
....
2.. Real Life Example (BEST)
-- Car pe Aap sirf: Start , Brake , Gear Use KArte Ho 
-- Engine ka internal logic nahi dekhte

- How to Implement Abstraction in C#?
1.. Using Abstract Class
-- abstract keyword use hota hai
-- Abstract methods ka body nahi hota
-- Child class ko implement karna compulsory hota hai
Example
abstract class Payment
{
    public abstract void Pay();
}
class CreditCardPayment : Payment
{
    public override void Pay()
    {
        Console.WriteLine("Payment done using Credit Card");
    }
}
....
2.. Using Interface (Most Used in Real Apps ⭐)
-- Interface pure abstraction provide karta hai
-- Interface pure abstraction provide karta hai
-- Multiple inheritance support karta hai
Example
interface IPayment
{
    void Pay();
}
class UpiPayment : IPayment
{
    public void Pay()
    {
        Console.WriteLine("Payment done using UPI");
    }
}

- When to Use Abstraction in Real Applications?
-- Jab future changes expected ho
-- Jab implementation hide karni ho
-- Jab multiple implementations ho
-- Jab loosely coupled code chahiye

- Jab future changes expected ho
-- Very small programs
-- Jab sirf ek hi implementation ho

- Interview
"Abstraction is the process of hiding implementation details and showing only essential features.
In C#, abstraction is implemented using abstract classes and interfaces."

## Q7 : What is Encapsulation? How to implement encapsulation in real applications? 
- What is Encapsulation?
"Encapsulation ka matlab hai data (variables) aur methods ko ek class ke andar bundle karna aur data ko direct access se protect karna."
👉 Data hide + controlled access = Encapsulation

- Technical Definition (Interview)
"Encapsulation is an OOPS concept that binds data and methods together and restricts direct access to data using access modifiers."

- How to Implement Encapsulation in C#?
-- Encapsulation C# me mainly 2 cheezon se implement hoti hai 👇
1.. Access Modifiers
2.. Properties (get / set)

- Code
1.. Without Encapsulation (Wrong Way)
class Account
{
    public int balance;
}
👉 Koi bhi balance change kar sakta hai (unsafe ❌)
....
2.. With Encapsulation (Correct Way)
class Account
{
    private int balance;

    public int Balance
    {
        get { return balance; }
        private set { balance = value; }
    }

    public void Deposit(int amount)
    {
        if (amount > 0)
            Balance += amount;
    }

    public void Withdraw(int amount)
    {
        if (amount > 0 && amount <= Balance)
            Balance -= amount;
    }
}
👉 Balance private
👉 Access sirf methods ke through

- Real Application Use Case
1.. Banking Systems : Banking Systems
2.. Employee Systems : Salary private , Getter method se view
3.. APIs : Data validation before update

- Data validation before update
1.. When NOT to Use Encapsulation?
2.. Temporary scripts

## Q8 : What is the difference between Abstraction and Encapsulation?
- Abstraction?
-- Sirf important cheez dikhana, internal details hide karna.
-- Focus: WHAT to show

- What is Encapsulation?
-- Data aur methods ko ek class me band karna aur data ko protect karna.
-- 👉 Focus: HOW to protect data

- Real Life One-Line Difference
-- Abstraction → “Kya kaam hota hai”
-- Encapsulation → “Kaise data secure hota hai”

## Q9 : What is Polymorphism and what are its types? When to use polymorphism?
- Definition
-- Polymorphism ka matlab hai “one name, many forms”.
-- 👉 Same method / function ka naam same, par behavior different hota hai.

- Real Life Example (BEST)
-- Friend ke saath → Friendly talk
-- Boss ke saath → Professional talk
👉 Naam same (Talk), behavior different

- Types of Polymorphism in C#
1.. Types of Polymorphism in C#
-- Method Overloading , Same method name , Different parameters , Static 
-- Code
class Calculator
{
    public int Add(int a, int b)
    {
        return a + b;
    }

    public int Add(int a, int b, int c)
    {
        return a + b + c;
    }
}
-- Compiler decide karta hai kaunsa method call hoga
.....
2.. Run-Time Polymorphism
-- Run-Time Polymorphism , virtual + override , virtual + override , Dynamic
-- Code
class Animal
{
    public virtual void Sound()
    {
        Console.WriteLine("Animal sound");
    }
}
class Dog : Animal
{
    public override void Sound()
    {
        Console.WriteLine("Bark");
    }
}

- When to Use Polymorphism?
1.. When Same Action, Different Behavior Chahiye
-- Pay() → UPI
-- Pay() → Credit Card
-- Pay() → Net Banking
....
2.. When Code Flexible Banana Ho
-- Future me new child class add ho
-- Existing code change na karna pade
....
3.. When You Want Loose Coupling
-- Parent reference use karo
-- Child implementation easily switch ho jaye
....
4.. In Real Applications (Very Common)
-- Logging systems
-- Payment gateways
-- Notification systems (Email, SMS, Push)

- When NOT to Use Polymorphism?
-- Very small programs
-- Jab behavior same hi rehna ho

- Interview
"Polymorphism allows methods to have different behavior with the same name.
It is of two types: compile-time (overloading) and run-time (overriding).
It is used when we need flexibility and different behavior for the same action"

## Q10 : What is Method Overloading? In how many ways a method can be overloaded?
- Defination
-- Method Overloading ka matlab hai:
-- Same method name,
-- Same class,
-- Different parameters.
-- Static Polymorphism Or Example OF Compile Time Polymorphism

- Real Life Example
-- Calculator
Add(2,3)
Add(2,3,4)
-- Naam same (Add)
-- Kaam thoda different

- In How Many Ways a Method Can Be Overloaded?
1.. In How Many Ways a Method Can Be Overloaded?
void Print(int a)
void Print(int a, int b)
2.. Different Types of Parameters
void Show(int a)
void Show(string a)
3.. Different Order (Sequence) of Parameters
void Display(int a, string b)
void Display(string b, int a)

- What is NOT Method Overloading?
-- Only return type change ❌
int Test()
string Test()   // ❌ Invalid
👉 Compiler confuse ho jayega
.....
-- Access modifier change ❌
public void Run()
private void Run()  // ❌ Invalid

- Interview
"Method Overloading allows multiple methods with the same name in the same class with different parameters.
It can be done in three ways: number, type, and order of parameters."

- Interview Tips
👉 Overloading inheritance ke bina bhi possible hai
👉 Overloading static methods ke saath bhi possible hai

## Q11 : When should you use method overloading in real applications?
- Simple Rule
-- When should you use method overloading in real applications?
-- Jab kaam same ho, lekin input different ho

- Examples
1.. Same Operation, Different Inputs
-- Same Operation, Different Inputs
Add(2, 3)
Add(2, 3, 4)
Add(2.5, 3.5)
👉 Operation same (Add)
👉 Inputs different
✔ Best case for overloading
.....
2.. To Improve Code Readability & Clean API
❌ Without Overloading
AddTwoNumbers()
AddThreeNumbers()
AddDoubleNumbers()
😕 Code confusing ho jata hai
✅ With Overloading
Add(int a, int b)
Add(int a, int b, int c)
Add(double a, double b)
✔ Easy to read
✔ Easy to use
.....
3.. Framework / Library Design
-- Real World Example (.NET)
Console.WriteLine("Hello");
Console.WriteLine(10);
Console.WriteLine(true);
👉 Same method name
👉 Different parameter types
.....
4.. When You Want Logical Grouping of Methods
👉 Similar kaam wale methods ko
👉 Ek hi naam ke andar group karna
Example 
Log(string message)
Log(string message, Exception ex)
Log(string message, LogLevel level)
.....
5.. Default Values Alternative (Older C#)
-- Pehle jab default parameters nahi hote the:
Print(string msg)
Print(string msg, bool isBold)
....
6.. Business Applications Example (VERY IMPORTANT)
📌 Payment System
Pay(double amount)
Pay(double amount, string currency)
Pay(double amount, string currency, string mode)
👉 Same action (Payment)
👉 Different details

- When NOT to Use Method Overloading?
1.. 🚫 Different Behavior Ho
SaveData()
DeleteData()
❌ Yahan alag names chahiye
....
2.. 🚫 Confusion Create Ho
Process(int id)
Process(long id)
⚠ Interview me bol sakte ho → Avoid confusion

- Interview
"Method overloading should be used when multiple methods perform the same operation but accept different parameters.
It improves readability, usability, and code maintainability."

## Q12 :  If two methods are same except return type, then methods are overloaded or what willl happen?
- In How Many Ways a Method Can Be Overloaded?
1.. In How Many Ways a Method Can Be Overloaded?
void Print(int a)
void Print(int a, int b)
2.. Different Types of Parameters
void Show(int a)
void Show(string a)
3.. Different Order (Sequence) of Parameters
void Display(int a, string b)
void Display(string b, int a)

- What is NOT Method Overloading?
-- Only return type change ❌
int Test()
string Test()   // ❌ Invalid
👉 Compiler confuse ho jayega
.....
-- Access modifier change ❌
public void Run()
private void Run()  // ❌ Invalid


## Q13 : What is the difference between Overloading and Overriding?
- Overriding
-- Multiple methods of same name are in different class.
-- Inheritance is used, as it is in different class.
-- Both methods have same signature.
-- It’s a run time polymorphism. 
-- Virtual & override keywords.
-- Can Be done Without Inhertance

- Overloading
-- Multiple methods of same name in single class.
-- No need of inheritance, as it is in single class.
-- All methods have different signature.
-- It’s a compile time polymorphism.
-- No special keyword used.
-- Inheritance is Necessary

## Q14 : If a method is marked as virtual, do we must have to "override" it from the child class?
-- No , Ovverriding Virtual Method Is Optional

## Q15 : What is the use of Overriding? When should I override the method in real applications?
- Use
"Overriding is used to modify and provide a new implementation of the method inherited from a base class.
"
## Q16 : What is the difference between Method Overriding and Method Hiding?
- Method Overriding – Kya Hota Hai?
-- Simple Defination
👉 Child class parent ke virtual method ko apna naya behavior deta hai
👉 Runtime pe decide hota hai kaunsa method chalega
-- ✔ Keywords Used
1.. virtual (Parent)
2.. override (Child)

- Method Hiding – Kya Hota Hai?
👉 Child class parent ke method ko hide kar deta hai
👉 Runtime polymorphism nahi hota
-- KeyWord Used : new
-- Example 
class Parent
{
    public void Display()
    {
        Console.WriteLine("Parent Display");
    }
}
class Child : Parent
{
    public new void Display()
    {
        Console.WriteLine("Child Display");
    }
}

- Key Difference
👉 Overriding = Runtime decision
👉 Hiding = Compile-time decision

- Differece Table
| Feature               | Method Overriding  | Method Hiding   |
| --------------------- | ------------------ | --------------- |
| Keywords              | virtual + override | new             |
| Inheritance           | Required           | Required        |
| Polymorphism          | Yes                | No              |
| Binding               | Runtime            | Compile time    |
| Parent reference call | Child method       | Parent method   |
| Behavior change       | Yes                | No (just hides) |

- When to Use What?
1.. ✔ Use Method Overriding When:
-- Runtime polymorphism chahiye
-- Parent behavior replace karna ho
-- Framework / real applications
.....
2.. ❌ Avoid Method Hiding When:
-- You want polymorphic behavior
-- It causes confusion
Method Hiding Is Rearly Used 

- Interview
"Method Overriding allows a child class to provide a new implementation of a parent’s virtual method and supports runtime polymorphism, whereas Method Hiding hides the parent method using the new keyword and is resolved at compile time."

- Interview Tip : 
👉 If method is not virtual → overriding not possible
👉 If override keyword missing → method hiding happens

## Q17 : Explain operator overloading ?
- Defination
-- Operator Overloading ka matlab hai:
👉 Existing operators (+, -, ==, etc.) ko user-defined classes ke liye use karna
👉 Operator ka meaning hum define karte hain

- Real Time Example
👉 Normally:
5 + 3 = 8
👉 Operator overloading me:
Point1 + Point2 = New Point

- Why Operator Overloading?
-- Code natural & readable ban jata hai
-- Mathematical / business logic easy lagta hai
-- Class ko primitive type jaise behave karwa sakte hain

- Example In C#
✔ Without Operator Overloading
Point p3 = p1.Add(p2);
✔ With Operator Overloading
Point p3 = p1 + p2;
👉 Same kaam, but 2nd way easy & clean hai

- Code
class Point
{
    public int X;
    public int Y;

    public Point(int x, int y)
    {
        X = x;
        Y = y;
    }

    public static Point operator +(Point p1, Point p2)
    {
        return new Point(p1.X + p2.X, p1.Y + p2.Y);
    }
}
Point p1 = new Point(2, 3);
Point p2 = new Point(4, 5);
Point p3 = p1 + p2;

- Important Rules (Interview Point ⭐)
1️⃣ Operator overloading static method hoti hai
2️⃣ Operator overloading class ke andar hi define hoti hai
3️⃣ All operators overload nahi ho sakte
4️⃣ At least one operand user-defined type hona chahiye

- ❌ Operators That CANNOT Be Overloaded
❌ .
❌ ?:
❌ sizeof
❌ typeof

- ✅ Operators That CAN Be Overloaded
✔ + - * /
✔ == !=
✔ < >
✔ ++ --

- Real World Use Case
Vector / Matrix calculation
Financial amounts (Money + Money)
Complex numbers
Geometry classes (Point, Distance)

- ❌ When NOT to Use Operator Overloading?
Jab logic confusing ho
Simple CRUD applications me
Jab meaning clear na ho