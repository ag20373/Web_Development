# 1. OOP Interview Questions (Encapsulation, Inheritance, Polymorphism, Abstraction)
## Q1 : OOPS Kya hai?
Answer: OOP ka matlab hai Object-Oriented Programming, jisme hum real-world entities (Car, Employee, Account) ko class aur object ke form mein represent karte hai.
4 main concepts hai: Encapsulation, Inheritance, Polymorphism, Abstraction.

## Q2 : Encapsulation kya hota hai?
Answer : 
- Encapsulation = data ko hide karna + getter/setter ke through access dena.
- Yeh ek capsule jaisa hota hai jo data aur methods ko bind karta hai.

Example : Bank account class — account balance ko private rakhte hai, aur deposit() / withdraw() method ke through access karte hai.

Real Life: ATM se paisa nikalte ho → andar ka balance directly nahi dekh sakte → bas interface (screen) ke through access.

class BankAccount {
    private double balance;

    public void Deposit(double amount) {
        balance += amount;
    }

    public double GetBalance() {
        return balance;
    }
}

## Q3 :  Inheritance kya hota hai?
Answer : 
- Inheritance = ek class ka feature dusri class mein reuse karna
- Ek parent (base) class hoti hai aur ek child (derived) class uske properties + methods inherit karti hai.

Example:
Car → SportsCar, ElectricCar.
Sabhi cars ke paas wheel honge (parent class se milega).

class Car {
    public void Drive() {
        Console.WriteLine("Car is running...");
    }
}

class SportsCar : Car {
    public void Turbo() {
        Console.WriteLine("Turbo ON");
    }
}

## Q4 : Polymorphism kya hota hai?
Answer : 
- Polymorphism = ek hi method ka alag-alag form mein kaam karna.
- 2 types : 
    1. Compile-time (Method Overloading)
    2. Run-time (Method Overriding)

Example (Overloading):
class Calculator {
    public int Add(int a, int b) => a + b;
    public double Add(double a, double b) => a + b;
}

Example (Overriding):
class Animal {
    public virtual void Sound() {
        Console.WriteLine("Animal sound");
    }
}
class Dog : Animal {
    public override void Sound() {
        Console.WriteLine("Dog barks");
    }
}

## Q5 : Abstraction kya hota hai?
Answer : 
- Abstraction = implementation details ko hide karna, sirf features dikhana.
- Abstract class / Interface ka use hota hai.

Real life: Car chalane ke liye engine kaise kaam karta hai yeh nahi dikhate, sirf steering, brake, accelerator diye jate hai.

## Q6 : Encapsulation aur Abstraction mein kya difference hai?
Ans : 
- Encapsulation = Data hiding (access modifiers).
- Abstraction = Implementation hiding (abstract class / interface).

Example :
 - Encapsulation → Bank balance private hai.
 - Abstraction → Car ke engine ki details hide hai.

## Q7 : Inheritance ke disadvantages kya hai?
Ans : 
1. Tight coupling ho jata hai (child class parent ke sath depend ho jati hai).
2. Agar parent mein change kiya toh child classes break ho sakti hai.
3. Multiple inheritance (C# mein directly allowed nahi, sirf interfaces ke through).

## Q8 : Polymorphism ka real life example do.
Ans : "Speak()" method alag-alag animals mein different behave karega.


# Abstract class vs Interface
## Theory 
1) Concept in Plain Words
-> Abstract Class :
    * Partially complete base class: kuch code ready, kuch abstract “to be provided by child”.
    * State (fields) rakh sakti hai, constructor ho sakta hai, virtual/abstract methods ho sakte hain.
    * Ek class sirf 1 abstract (or any) class se inherit kar sakti hai.
    * Analogy: “Base Vehicle” jisme fuel capacity, odometer jaise shared members already defined hain. Har specific vehicle (Car/Bike) apna Start() ka tarika deta hai.

-> Interface : 
    * Contract/role: “yeh members implement karne hi honge”
    * Multiple interfaces implement kar sakte ho
    * State (instance fields) nahi hoti. (Properties declare kar sakte ho, par backing field class mein hoti hai.)
    * Modern C# (8+) mein default interface methods bhi possible hain (par public APIs mein soch-samajh ke use karo).
    * Analogy: “IDrivable”, “IPayable”, “ILogging”: koi bhi cheez jo drive ho sakti hai, pay kar sakti hai, log kar sakti hai — woh yeh role implement kar sakti hai, chahe woh Car ho, Robot ho, ya GameCharacter.

2) Side-by-Side Differences
| Topic             | Abstract Class                     | Interface                                                           |
| ----------------- | ---------------------------------- | ------------------------------------------------------------------- |
| Purpose           | Base type + shared code            | Capability/contract                                                 |
| State (fields)    | ✅ allowed                          | ❌ instance fields not allowed                                       |
| Constructor       | ✅ yes                              | ❌ no (but static members possible in modern C#)                     |
| Methods           | abstract/virtual/concrete          | typically abstract; C# 8+ default impl possible                     |
| Properties/Events | ✅                                  | ✅                                                                   |
| Inheritance       | Single class inheritance           | Multiple interfaces                                                 |
| Access Modifiers  | public/protected/private etc.      | members effectively public (default impl ke sath modifiers limited) |
| Versioning        | New virtual method add karna safer | New method add = breaking (unless default impl)                     |
| Use when          | Common state/behavior share        | Cross-cutting role across unrelated types                           |

3) Real-Life Modeling Examples
-> Ride-Hailing (Uber/Ola)
    * Abstract class: Vehicle → shared state: FuelLevel, Odometer; behavior: Refuel().
    * Interfaces: 
        IDrivable (drive kar sakta),IElectric (charge kar sakta),IShareLocation (live location share).
    * Why both? Vehicle family me common code abstract class se aata hai; roles interfaces se.

-> Payments in E-commerce
    * Abstract class: PaymentProviderBase (API keys, retry policy, common HTTP client).
    * Interfaces: IPaymentMethod (authorize/capture/refund), IFraudCheckable, IRefundable.
    Alag providers (Razorpay, Stripe, PayPal) same base infra share karte hain; but koi Wallet/UPI/BNPL capabilities ke roles se express hote hain.

## Q1 : Abstract class kya hoti hai?
Ans : Abstract class ek blueprint class hoti hai jisme kuch kaam ready hota hai aur kuch kaam bacha hota hai jo “child class” complete karegi.

Example:
Socho ek School Notebook factory hai — woh lines aur margin ready karke deta hai, par tumko khud likhna hota hai.

abstract class Animal {
    public abstract void MakeSound();  // child ko define karna hi padega
}

class Dog : Animal {
    public override void MakeSound() {
        Console.WriteLine("Bark");
    }
}

## Q2 : Interface kya hota hai ?
Ans : Interface ek contract hai jo bolta hai — “jo bhi class isko implement karegi, usko yeh kaam karna hi hoga.”

Example:
Socho tumhare school me rule hai:

“Jo bhi student ‘Cricket Team’ join karega, usko playCricket() karna aana chahiye.”
Interface = woh rulebook hai.

interface ICricketer {
    void PlayCricket();
}

class Student : ICricketer {
    public void PlayCricket() {
        Console.WriteLine("I can bat and bowl");
    }
}

## Q3 : Abstract class aur Interface mein simple difference?
Ans : Abstract class = partially ready notebook (kuch bana hua + kuch blank).
Interface = rulebook (sirf bolta hai kaam karna hai, implementation tum karo).

## Q4 : Kya abstract class ka object ban sakta hai?
Ans : Nahi. Sirf uski child (derived) class ka object banega.

Example:
Tum "Animal" ka directly object nahi bana sakte.
Tum "Dog" ya "Cat" ka bana sakte ho.

## Q5 : Kya interface ka object ban sakta hai?
Ans : Direct nahi, par ek reference ban sakta hai.

Example :
1. “ICricketer” rulebook khud khel nahi sakta.
2. Lekin ek student jo cricketer hai, woh khel sakta hai.

## Q6 :  Abstract class aur Interface mein kya common hai?
Ans : 
- Dono me “abstract methods” ho sakte hain.
- Dono inheritance/implementation ke through use hote hain.
- Dono ka purpose → Polymorphism allow karna.

## Q7 : Abstract class aur Interface mein differences?
Ans : 
srn Feature	             Abstract Class	    Interface
1   Purpose              Base blueprint      Rulebook/Contract
2   Constructor          Allowed             not allowd(only methods/properties)
3   Multiple inheritance not possible        Possible
4   Partial implemtition yes                 till C# 8

## Q8 : Real life example dono ka saath?
Ans : 
- Abstract class (Vehicle): har vehicle ka fuel tank aur wheels common hote hain.

- Interface (IDrivable): koi bhi cheez jo drive ho sakti hai, chahe woh Car ho ya Scooter ya Robot, usne Drive() method implement karna hi hoga.

## Q9 : Ek class ek hi abstract class ko inherit kyu kar sakti hai par multiple interfaces implement kyu kar sakti hai?
Ans : Kyuki agar ek child ke 2 parents ho aur dono same method de, toh confusion ho jayega (“Diamond Problem”). Isliye class inheritance single hoti hai.
Interfaces ke case me sirf “contract” hote hain, toh conflict kam hota hai.

## Q10 : Kya abstract class me constructor hota hai?
Ans : Haan. Use child class ke object banate time call hota hai.
Example:
Ek base school form hai jisme kuch details fill automatically hoti hain (school name, board). Phir tum apna naam/dob likhte ho.

## Q11 : Abstract class kab use karni chahiye aur Interface kab?
Ans :
1. Abstract class: Jab classes ek family me ho aur unka base code/state common ho.
2. Interface: Jab tum ek role/capability dena chahte ho jo alag-alag families me lag sakta hai.

Example :
- Abstract class: Vehicle → Car, Bike, Truck.
- Interface: IDrivable → Car, Bike, RobotCar, even Drone.

## Q12 : Agar tum ek Bird class banate ho, toh Abstract class ya Interface?
Ans : 
- Bird = Abstract class (kyunki sab birds ke paas wings, beak common hote hain).
- IFlyable = Interface (kyunki sab birds fly nahi karte, jaise Penguin).

## Q13 : Can interface have default methods?
Ans : Haan (C# 8 se). Matlab interface ke andar method ka default implementation likh sakte ho. Lekin practical projects me ise carefully use karte hain.

## Q14 : Performance difference hai?
Ans : Dono ka dispatch (method call) vtable se hota hai. Performance lagbhag same. Design choice matter karti hai, speed nahi.

## Q15 : Real-world software example jisme dono ek sath use hote hain?
Ans : E-commerce Payment System:
1. Abstract class: PaymentGatewayBase (common things: API keys, logs, retries).
2. Interface: IPaymentMethod (Authorize/Pay/Refund).
Har provider (Razorpay, PayPal, Stripe) → abstract class se base lega, aur multiple interfaces (IRefundable, IFraudCheckable) implement karega.

## Q16 : Agar tumhare paas ek class Car hai, aur usko tumhe IDrivable, IMusicPlayer, IACController banana hai, kya possible hai?
Ans : Haan, kyunki ek class multiple interfaces implement kar sakti hai.

## Q17 : Diamond Problem kya hai aur C# me kaise solve hota hai?
Ans : Diamond problem tab hota hai jab ek class 2 parent classes se inherit kare aur dono me same method ho → confusion.
C# me multiple class inheritance allowed nahi hai, isliye ye issue hota hi nahi.

## Q18 : Abstract class me 100% abstract methods ho to Interface hi kyu na banaye?
Ans : Correct, agar ek abstract class sirf abstract methods rakh rahi hai (aur koi state nahi) → usko interface banana better hai.

## Q19 : Abstract class ke andar static methods ho sakte hain?
Ans : Haan ho sakte hain. ye methods child class ka bina bhi call kiye ja sakta hain

## Q20 : Interfaces ke andar fields kyun allowed nahi hote?
Ans : Kyuki interface ek rulebook hai, aur rulebook me “state” nahi hoti. State hamesha class me hoti hai jo us rule ko implement karti hai.

# Virtual vs Override vs New.
## Q1 : Basic Definations
Ans : 
1. Virtual 
- Base class me method ko virtual banane ka matlab → “ye method child class me change kiya ja sakta hai (override ke liye open hai)”.
- Agar override na kare to default base version hi chalega.

2. override
- Derived class me method ko override karna matlab → “base class ke virtual method ko replace karna”.
- Run-time pe decide hota hai kaunsa chalega (runtime polymorphism).

3. new 
- Agar child class me method new keyword ke saath likhte ho → matlab base class ka method hide karna chahte ho.
- Lekin base reference se call karoge to base wala hi chalega.

## Q2 : School Style Example
Ans : Socho tumhare school me ek Teacher hai aur ek MathTeacher hai.
- virtual: Teacher bolta hai → “Main ek general lecture de sakta hoon, lekin agar MathTeacher chahe toh apna version padha sakta hai.”
- override: MathTeacher bolta hai → “Main apna special math lecture padhata hoon jo Teacher wale lecture ko replace karega.”
- new: MathTeacher bolta hai → “Mere paas ek bilkul alag lecture hai, jo Teacher wale lecture se unrelated hai.”

## Q3 : Code Example
Ans : 
using System;

class Teacher
{
    public virtual void Teach()   // virtual: can be overridden
    {
        Console.WriteLine("Teacher is teaching a general subject");
    }
}

class MathTeacher : Teacher
{
    public override void Teach()   // override: replacing base Teach()
    {
        Console.WriteLine("MathTeacher is teaching Algebra");
    }

    public new void Explain()      // new: hiding base Explain()
    {
        Console.WriteLine("MathTeacher explains Math concepts only");
    }
}

class Program
{
    static void Main()
    {
        Teacher t1 = new Teacher();
        t1.Teach();   // Teacher is teaching a general subject

        Teacher t2 = new MathTeacher();
        t2.Teach();   // MathTeacher is teaching Algebra (runtime polymorphism)

        MathTeacher t3 = new MathTeacher();
        t3.Explain(); // MathTeacher explains Math concepts only

        Teacher t4 = new MathTeacher();
        // Base reference - new method hidden, so base version called
        // Agar Teacher me Explain hota to wahi call hota
        // Agar Teacher me Explain hi nahi hota, toh call hi nahi kar paate
    }
}

## Q4 : Important Interview Points
Ans : 
1. Virtual method : Base Class me hone zaroori hai.
2. Override method: derived class me hona zaroori hai, aur base method virtual/abstract hona chahiye.
3. New keyword: base method ko override nahi karta, bas hide karta hai.
4. Polymorphism sirf override me hoti hai (runtime pe decide).
5. Agar new use karo aur base reference se call karo → base wala method chalega.

## Q5 : Real Life Analogy
Ans : 
1. Virtual = Principal bolta hai: “Main ek speech deta hoon, teachers chahe toh apna version de sakte hain.”

2. Override = Math Teacher principal ka speech apne style me deta hai (same topic, different explanation).

3. New = Sports Teacher ek alag hi speech deta hai (same naam ka function ho sakta hai, lekin base se unrelated).

# Sealed class / method.
## Q1 : Sealed Class kya hoti hai?
Ans : sealed class wo hoti hai jisko inherit nahi kar sakte , Matlab: agar tum us class ko base class banana chahte ho, compiler allow nahi karega.

School Analogy :
1. Socho tumhare school ka Principal ek “sealed class” hai.
2. Principal ka post inherit nahi ho sakta — tum principal ke child ho sakte ho, par tum automatically next principal nahi ban jaoge.

sealed class Principal
{
    public void Announce()
    {
        Console.WriteLine("Principal is making an announcement");
    }
}

// ❌ Error: Cannot derive from sealed class
class VicePrincipal : Principal
{
}


## Q2 : Sealed Method kya hota hai?
Ans : 
- Jab ek class ke method ko sealed banate ho, iska matlab hai → derived classes us method ko override nahi kar sakti.
- Lekin base class me wo method override hone ke baad hi sealed banaya ja sakta hai.

School Analogy : 
- Socho ek Math Teacher hai jiska ek “teach()” method hai.
- Usne apna padhane ka style final kar diya (sealed).
- Matlab uske niche koi aur teacher us style ko aur change nahi kar sakta.

class Teacher
{
    public virtual void Teach()
    {
        Console.WriteLine("General teaching");
    }
}

class MathTeacher : Teacher
{
    public sealed override void Teach()   // sealed method
    {
        Console.WriteLine("MathTeacher teaches algebra in fixed way");
    }
}

class JuniorMathTeacher : MathTeacher
{
    // ❌ Error: Cannot override sealed method
    // public override void Teach() { }
}

## Q3 : Why use Sealed ?
Ans : 
1. Security → Kisi ko class/method badalna allow na karna.
2. Performance → CLR (runtime) sealed methods ko optimize karta hai (fast dispatch).
3. Design clarity → Jo cheez logically further extend nahi honi chahiye, usko lock kar do.

## Q4 : Difference Between Sealed Class vs Sealed Method
Ans : 
| Feature | Sealed Class                    | Sealed Method                            |
| ------- | ------------------------------- | ---------------------------------------- |
| Meaning | Class ko inherit nahi kar sakte | Method ko override nahi kar sakte        |
| Use     | Final class banane ke liye      | Final method banane ke liye              |
| Example | `sealed class String { }`       | `public sealed override void ToString()` |

## Q5 : Real-Life Examples
Ans : 
* Sealed Class : 
- C# ka System.String ek sealed class hai → Matlab koi bhi "Hello" string ke base class bana ke usko inherit nahi kar sakta.
- Kyunki string ka behavior fixed hai (immutability).

* Sealed Method : 
- Ek bank system me CalculateInterest() ko sealed kar diya jaata hai taaki koi child class interest ka calculation galat tareeke se override na kare.

## Q6 : Interview Ready Q&A
1. Sealed class ka object bana sakte ho?
Ans : Haan, sealed class ka object banega, bas inherit nahi hoga.

2. Sealed method bina override kiye bana sakte ho?
Ans : Nahi. Sealed method tabhi banega jab wo method pehle override ho chuka ho.

3. Sealed class kyun use karte hain?
Ans : Security, optimization, aur design enforce karne ke liye.

4. Sealed aur Abstract opposite hote hain kya?
Ans : Abstract class → extend karna compulsory. , Sealed class → extend karna forbidden.

# Static class vs Non-static.
## Q1 : Static class kya hai?
Ans : Ek class jo static keyword se banti hai aur uska object create nahi hota. Sirf static members rakhti hai.
Example: System.Math

## Q2 : Non-static class kya hai?
Ans : Normal class jo static keyword ke bina hoti hai. Uska object ban sakta hai aur usme static + non-static dono members hote hain.
Example: Student, Car

## Q3 : Static class ka object kyun nahi ban sakta?
Ans : Kyunki iska purpose utility/helper functions provide karna hota hai, jo sab ke liye common hote hain.

## Q4 : Non-static class me static members ho sakte hain kya?
Ans : Haan, ek non-static class ke andar static fields/methods ho sakte hain (wo sab objects ke liye common rahenge).

## Q5 : Example do static aur non-static class ka real world se.
Ans : Static = Formula Book (ek hi copy sab ke liye), Non-Static = Student (har student alag-alag).

## Q6 : Static class aur singleton class me difference kya hai?
Ans : Static class ekdum static hai (inheritance/instance allowed nahi),
Singleton ek normal class hoti hai jiska sirf ek object banne diya jata hai (private constructor + static instance).

## Q7 : Static constructor kya hota hai?
Ans : Ek constructor jo sirf static members initialize karta hai aur program me automatically ek hi baar call hota hai.

## Q8 : Kya static class kisi interface ko implement kar sakti hai?
Ans : Nahi, kyunki static class ka object nahi ban sakta, aur interface ka contract object ke through fulfill hota hai.

## Q9 : Kya static class inherit kar sakti hai ya usse inherit kiya ja sakta hai?
Ans : Nahi, static class inherit nahi kar sakti aur koi class usse inherit bhi nahi kar sakti.

## Q10 : Static aur instance members me difference kya hai?
Ans : 
- Static → sab objects ke liye common (ek hi memory).
- Instance → har object ke liye alag memory.

# Q11 : Agar ek non-static class me static aur non-static dono members hain, to unhe access kaise karenge?
Ans : Static member → ClassName se call karenge.
      Non-static member → Object banake call karenge.

## Q12 : Performance ke perspective se static class ka use kyun faydemand hai?
Ans : Kyunki ek hi memory allocation hota hai, bar-bar new object create karna nahi padta.

## Q13 : Kya ek static class generic ho sakti hai?
Ans : Nahi. C# me static class ko generic banana allowed nahi hai.

## Q14 : Agar ek non-static class me static constructor ho to uska behavior kya hoga?
Ans : Wo static members ko initialize karega aur automatically sirf ek baar run hoga, chahe kitne bhi objects bano.

## Q15 : Static method aur instance method me main difference kya hai?
Ans : Static method bina object banaye call hota hai, instance method ke liye object banana compulsory hai.

## Q16 : Kya ek static class multiple threads ke sath safe hai (Thread-Safe)?
Ans : Agar static members ko properly readonly ya lock ke sath manage kiya ho, tabhi safe hoga. Warna data race issue aa sakta hai.

## Q17 : CLR (Common Language Runtime) static classes ko memory me kaise handle karta hai?
Ans : Static members ko High Frequency Heap me store kiya jata hai aur ye program ke end tak memory me rehte hain.

## Q18 : Static keyword ka misuse kya ho sakta hai?
Ans : Har jagah static use karne se code tightly coupled ho jata hai, unit testing mushkil ho jati hai, aur memory leak ke chances badh jate hain.

## Q19 : Kya ek non-static class ke andar nested static class ho sakti hai?
Ans : aan, ho sakti hai. Nested static class generally helper ke liye use hoti hai.

## Q20 : Agar ek non-static class me sirf static members ho, to us class ko static bana dena chahiye kya?
Ans : Haan, best practice ke liye static bana dena chahiye, taki koi galti se uska object na banaye.

-> Real World Analogy 
Static Class = School ki "Notice Board" → Sab ke liye ek hi, object banane ki zarurat nahi.
Non-Static Class = Har "Student" → Alag-alag data, har ek ka object banega.