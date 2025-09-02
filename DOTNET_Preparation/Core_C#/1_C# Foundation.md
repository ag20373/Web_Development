# 1. Data Types (Value Types vs Reference Types)
## Q1 : What are value types and reference types in C#? Give examples.
Ans : C# mein 2 tarah ke types hote hain – Value types aur Reference types.
-> Value Type : apna data directly store hote hain - Value types aur reference types.
-> Reference types data ko memory mein alag store karte hain aur variable ke andar sirf address/reference rakha hota hai. Example: string, object, class, array, interface.

## Q2 : How are value types stored in memory (stack vs heap)?
Ans : Generally ,value types stack par store hote hain, aur reference types heap par.
Stack fast hai, lekin size limited hota hai. Heap thoda slow hai, but bada hota hai.

## Q3 : Is string a value type or reference type? Why does it behave differently?
Ans : String actually reference type hai, lekin behave value type jaisa karta hai kyunki immutable hota hai. Matlab ek baar ban gaya toh modify nahi hota, new memory allocate hoti hai.
Isliye jab string concatenate karte hain, har baar naya object banta hai.

## Q4 : What happens when you assign one value type to another? (copy vs reference)
Ans : Jab value type assign karte ho, toh copy banta hai. Matlab dono independent hote hain.
Lekin reference type assign karoge toh sirf reference share hota hai, dono variable same object ko point karenge.

Real World Example : 
- Value type → ek aadmi ke Aadhar card ki xerox nikal li – copy hai, asli se koi lena dena nahi.
- Reference type → ek hi ghar ka address 2 logon ko diya – dono same ghar ke andar dekh rahe hain.

## Q5 : Can a struct contain a reference type?
Ans : 
Interview Answer - “Ji haan, struct ke andar reference type fields ho sakte hain, jaise string ya object.
Lekin phir bhi struct khud ek value type hi rahega.”

Real-world example: 
Samjho tumhare wallet (struct) ke andar ek ATM card (reference) rakha hai. Wallet tumhare paas ek value type hai, lekin card ek reference bank ke database ko point karta hai.

## Q6 : Difference between struct and class.
Ans : 
1. Struct = Value type, Class = Reference type
2. Struct = stored on stack, Class = heap
3. Struct = no inheritance, Class = supports inheritance
4. Struct = lightweight (used for small objects), Class = heavy, full OOP features
5. Struct cannot have parameterless constructor, Class can

Real Life Example : 
 - Struct → Visiting card (simple info, lightweight, easily copied).
 - Class → Office Employee record in HR system (big data, multiple relationships).

## Q7 : Why are enums considered value types?
Ans : Enum actually internally ek integral type (int, byte, etc.) ke base par banta hai, aur ye value type hota hai.
Isliye enum bhi ek value type hota hai.

## Q8 : Can value types be null? How?
Ans : Normally value types null nahi ho sakte.
Lekin C# mein Nullable<T> ya int? syntax use karke hum null allow kar sakte hain.

## Q9 : Value aur Reference type ke memory allocation me kya difference hai?
Ans : Value type directly stack me store hota hai. Reference type ka reference stack me hota hai aur actual object heap me store hota hai.

## Q10 : Garbage Collector kiske liye kaam karta hai?
Ans : GC sirf heap objects (reference types) ko manage karta hai. Stack me stored value types automatically handle ho jate hain.

## Q11 : Boxing aur Unboxing kya hai?
Ans :  Boxing = Value type ko reference type me convert karna.
Unboxing = Reference type ko wapas value type me convert karna.

## Q12 : Deep copy aur Shallow copy me difference?
Ans : 
- Shallow copy = Sirf reference copy hota hai (nested object shared hote hain).
- Deep Copy =  Deep copy = Naya object + uske andar ke nested objects bhi naya create hote hain.

## Q13 : Stack aur Heap me memory management kaise hota hai?
Ans : Stack = Fast, auto-cleaned when scope khatam hota hai.
Heap = Slow (GC ke through clean hota hai). Reference types heap me allocate hote hain.

## Q14 : String interning kya hota hai?
Ans : CLR ek string pool banata hai. Same literal string repeat hone par naya object create nahi karta, pool ka existing reference deta hai → performance improve hoti hai.

## Q15 : Value equality aur Reference equality me difference?
Ans : Value equality → Do objects ka content same hai ya nahi (Equals).
Reference equality → Do variables same memory address point kar rahe hain ya nahi (==).

## Real Life Based Q&A
## Q16 : Q16. Agar tum ek Trading System bana rahe ho aur tumhe real-time price ticks store karne hain → Value type ya Reference type?
Ans : Price tick ek chhoti numeric value hoti hai (double/int) → Value type sahi hai (fast access + low memory overhead).

## Q17 : Agar ek Employee object hai jisme multiple properties hain (Name, Address, Skills list) → kya use karoge?
Ans : Employee ek complex entity hai → Class (Reference type) use karna chahiye.

## Q18 : Gaming app me player ka score frequently update hota hai. Score ko Value type banaoge ya Reference type?
Ans :  Score ek numeric value hai → Value type best hai.

## Q19 : High-performance system me Value type prefer karna chahiye ya Reference type?
Ans : Mostly Value type, kyunki stack allocation fast hota hai. Lekin jab object complex aur large ho tab Reference type prefer karte hain.

## Q20 : Dictionary me Value type aur Reference type store karne par kya fark hoga?
Ans : 
1. Agar Value type hai toh dictionary me ek nayi copy store hogi.
2. Agar Reference type hai toh dictionary me sirf reference store hoga. Agar object change hoga toh dictionary ke andar bhi reflected milega.

# 2. var, dynamic, object
## Q1 : Difference between var, dynamic, and object ?
👉 Interview Answer:
 - var → Type compile time pe decide hota hai (compiler ko right-hand value se pata chalta hai). After that, type fix ho jata hai.
 - dynamic → Type runtime pe decide hota hai. Matlab compiler check nahi karega, error runtime pe milega.
 - object → Sabka parent class hai. Lekin jab use karte ho to boxing/unboxing ya explicit casting karni padti hai.

## Q2 : When is var resolved → compile time or runtime?
👉 Answer:
“var always compile-time pe resolve hota hai. Matlab compiler ko usi waqt pata chal jata hai ki type kya hai.”
var x = 10;   // compiler makes it int
x = "hello";  // ❌ error at compile time

## Q3 : When is dynamic resolved → compile time or runtime?
👉 Answer:
“dynamic ka type runtime pe decide hota hai. Compile-time pe compiler error nahi dega.”

👉 Example:
dynamic d = 10;
d = "hello";   // valid
d = new List<int>(); // valid
int len = d.Length;  // if not found, ❌ runtime error

## Q4: Why is dynamic slower than var?
👉 Answer:
“dynamic slower hai kyunki compiler usko runtime pe bind karta hai reflection ke through. Var already compile time pe fix hota hai, isliye fast hai.”

👉 Real-world example:
var = rail ticket reservation (seat fixed hai before journey).
dynamic = general ticket (seat decide hoga runtime pe train me chadne ke baad).

## Q5 : Is object type checked at compile time?
👉 Answer:
“Nahi. object type check runtime pe hota hai, lekin difference ye hai ki use karne ke liye tumhe explicit casting karni padti hai.”

object obj = "hello";
string s = (string)obj; // ✅ works
int i = (int)obj;       // ❌ runtime error

## Q6 : Can you cast dynamic to object? Vice versa?
👉 Answer:
“Bilkul, dynamic aur object dono ek dusre me cast ho sakte hain because internally dynamic bhi object hi hai.”

👉 Example:
dynamic d = "hello";
object o = d;    // dynamic -> object

object obj = 123;
dynamic dy = obj; // object -> dynamic

## Q7 : Can var be used as a method return type or parameter type?
Ans : “Nahi, var ko sirf local variables ke liye use kar sakte hain. Method parameter ya return type ke liye var allowed nahi hai.”

## Q8 : Agar Reflection ya ExpandoObject se dynamic property access karni hai toh kis ka use karenge?
Ans : dynamic (kyunki wo runtime pe property bind karta hai).

## Q9 : dynamic ka performance issue kyun hota hai?
Ans : Kyunki har access pe runtime binder call hota hai. Isliye heavy loop ya high performance system me avoid karna chahiye.

## Q15. Real project me tum dynamic kab use karoge?
Ans : Reflection, COM objects, ExpandoObject, JSON parsing jaise scenarios me jaha compile-time type pata nahi hota.

## Q16 : Tum Trading System bana rahe ho aur data types predefined hain (int, decimal) → kya use karoge?
Ans : var (compile-time safety aur fast performance).

## Q17 : Agar tumhe Excel/Word COM interop karna ho toh kya use karoge?
Ans : dynamic (kyunki COM objects ke members compile-time pe available nahi hote).

## Q18 : Agar tumhe heterogeneous collection (mixed data) store karna ho toh kya use karoge?
Ans : Ans: object, kyunki wo sabka base type hai. Example → ArrayList.

## Q19 : JSON data parse karte waqt jisme property ka structure compile-time pe nahi pata → kya use karoge?
👉 Ans: dynamic (Newtonsoft JSON .DeserializeObject<dynamic>()).

## Q20. Agar tumhe strongly-typed aur performance oriented code likhna hai toh kis ka prefer karoge?
👉 Ans: var (kyunki type safe aur fast hai).

## Summary : 
“Sir, var compile-time pe type fix karta hai, dynamic runtime pe, aur object sabka parent hai but explicit casting chahiye hoti hai. Var fast hai, dynamic thoda slow hai kyunki reflection use hota hai. Var sirf local variable ke liye use hota hai, return/parameter ke liye nahi.”

# 3. Nullable Types in C#
## Q1: What are nullable types in C#?
👉 Interview Answer:
“Normally value types (like int, bool, double) null hold nahi kar sakte.
Nullable types allow karte hain value type ko null store karne. Ye Nullable<T> ya ? syntax se hota hai.”

👉 Example:
int? age = null;   // valid
int age2 = null;   // ❌ not allowed

👉 Real-world Example:
Exam marks → har student ka marks number hoga, but agar student exam me baitha hi nahi toh marks = null ho sakta hai.

## Q2 : Difference between int? and Nullable<int>.
👉 Interview Answer:
“Dono same cheez hain. int? sirf Nullable<int> ka shorthand hai.
Compile time pe compiler int? ko Nullable<int> me convert kar deta hai.”

int? a = 5;              // shorthand
Nullable<int> b = null;  // long form

## Q3: How do you check if a nullable has a value? (HasValue vs Value)
👉 Interview Answer:
- HasValue → bool return karta hai (true/false)
- Value → actual value deta hai, but agar null ho to exception throw karega

👉 Example:
int? x = null;
if (x.HasValue)
    Console.WriteLine(x.Value);  // ❌ safe check
else
    Console.WriteLine("No value");

## Q4 : Explain null-coalescing operator ?? with example.
👉 Interview Answer:
“?? ka use hota hai ek default value dene ke liye jab variable null ho.”

👉 Example:
int? marks = null;
int finalMarks = marks ?? 35;  // output = 35

## Q5 : Explain null-conditional operator ?. with example.
👉 Interview Answer:
“?. ka use hota hai null check karne ke liye bina explicit if condition likhe. Agar variable null hoga toh exception nahi aayega, bas null return karega.”

## Q6 : Can reference types be nullable (C# 8 feature)?
👉 Interview Answer:
“Ji haan, C# 8 ke baad se nullable reference types concept aaya hai.
Isme aap string? likh ke compiler ko bata sakte ho ki yeh null hold kar sakta hai.
Ye feature compile-time warnings deta hai taaki null reference exception avoid ho.”

string? name = null;   // allowed
string fullName = null;  // ⚠ warning in C# 8+

## Q7 : Agar ek nullable variable ko non-nullable me assign karna ho toh kaise karenge?
👉 Ans: Ya toh cast karna hoga ya GetValueOrDefault() ya null-coalescing operator (??) use karna hoga.

## Q8 : Nullable lifting operators kya hote hain?
👉 Ans: Agar Nullable types ke saath arithmetic ya comparison operators use karte ho toh wo properly null handle karte hain.
int? a = 5;
int? b = null;
Console.WriteLine(a + b); // null

## Q9 : Nullable types aur LINQ me kya problem hoti hai?
Ans : Nullable values ko filter karne ke liye hamesha null-check lagana padta hai warna exceptions aate hain.

## Summary 
“Sir, nullable types allow karte hain value types ko null store karne. int? is just shorthand for Nullable<int>. Hum HasValue aur Value use karke check karte hain, aur shortcut ke liye ?? aur ?. operators use karte hain. C# 8 se reference types bhi nullable declare ho sakte hain for better null-safety."


# 4. const vs readonly vs static readonly
## Basic Concept 
1. const 
- Complite time 
- value fix hoti ha compile time pa
- Sirf primitive types (int, string, etc.) ke saath mostly use hoti hai.
- Auto static hota hai.

2. readonly
- Value set ho sakti hai → constructor ke time ya initialization ke time.
- Compile time pe fix nahi hoti, run-time pe decide ho sakti hai.
- Instance level bhi ho sakti hai.

3. static readonly
- Readonly + static ka combo.
- Value sirf ek baar set hoti hai → static constructor ya initialization ke time.
- Shared across all instances.

## Q1 : const aur readonly me basic difference kya hai?
Ans : 
1. const → Compile-time constant.
2. readonly → Run-time pe constructor me assign ho sakta hai.

## Q2 : Agar mujhe PI (3.14) store karna ho toh kya use karunga?
Ans : const, kyunki PI kabhi change nahi hota aur compile-time pe fix hai.

## Q3 : Agar mujhe ek DateTime store karna hai jo run-time pe decide hoga (jaise object create hone ka time), toh kya use karunga?
Ans : readonly, kyunki wo compile-time pe fix nahi hai.
public readonly DateTime CreatedAt;
public MyClass()
{
    CreatedAt = DateTime.Now;
}

## Q4 : Agar mujhe ek value chahiye jo sirf ek hi baar initialize ho aur saare objects ke liye common ho, toh kya use karunga?
Ans : public static readonly Guid AppId = Guid.NewGuid();

## Q5 : const automatically static hota hai?
Ans : Haan, const automatically static hota hai, lekin explicitly static const likhna allowed nahi hai.

## Q6 : readonly ko multiple constructor me alag-alag value de sakte hain?
Ans : Haan, kyunki wo run-time pe decide hota hai.
public readonly string Mode;
public MyClass(bool isProd)
{
    Mode = isProd ? "Production" : "Development";
}

## Q7 : Agar mujhe ek server ka Base URL store karna hai jo run-time config file se aata hai, toh kaunsa use karunga?
Ans : static readonly, kyunki wo ek hi baar load hoga aur sab objects ke liye same rahega.
public static readonly string BaseUrl = ConfigurationManager.AppSettings["BaseUrl"];

## Q8 : Agar ek const variable ki value change karni ho toh kya hoga?
Ans : Possible nahi hai, compile-time pe hi error dega.

## Q9 : readonly variable ko assignment kitni baar kar sakte ho?
Ans : Ek baar → ya toh declaration pe, ya constructor ke andar.

## Q10 : static readonly aur readonly me kya difference hai?
Ans : 
readonly → Per object instance alag ho sakta hai.
static readonly → Pure class ke liye ek hi value hogi, sab instances share karenge.

## Q11 : const aur static readonly ke IL (Intermediate Language) level me difference kya hai?
Ans : 
- const → Value IL me replace ho jati hai (hard-coded).
- static readonly → Value ek field me store hoti hai aur reference hota hai.

## Q12 : Agar tum ek const ko DLL me define karo aur dusra project usko use kare, aur tum const ki value change karke DLL recompile karo, toh dusre project ko kya karna hoga?
Ans : Dusre project ko bhi recompile karna hoga, kyunki const compile-time substitution karta hai.

## Q13 : readonly me agar reflection se value change karoge toh possible hai kya?
Ans : Haan, theoretically reflection se readonly fields change kiye ja sakte hain, lekin ye best practice nahi hai.

## Q14 : Performance difference const vs readonly vs static readonly?
Ans : 
- const → Fastest (inline replace hota hai).
- static readonly → Thoda slower (field access hota hai).
- readonly → Per-instance memory lagta hai.

## Q15 : Kya reference type ke saath const use kar sakte ho?
Ans : Sirf string ke saath. Baaki sab reference types ke liye static readonly use karna padta hai.

# 5. Type casting (implicit, explicit, as, is, pattern matching).
## Q1 : Implicit aur Explicit casting me kya difference hai?
Ans : 
- Implicit safe hai (chhoti → badi type, no data loss).
int a = 50;
double b = a; // implicit

- Explicit unsafe hai (badi → chhoti type, data loss ho sakta hai).
double d = 10.7;
int i = (int)d; // 10

## Q2 : as operator ka use kyun karte hain?
Ans : Kyunki as exception throw nahi karta, agar cast fail ho toh null return karta hai.

## Q3 : is operator kya karta hai?
Ans : Type checking karta hai → object given type ka hai ya nahi.

## Q4 : Agar tum ek object ko string me convert karna chahte ho toh kis method ka use karoge?
Ans : as operator safe hai.
object obj = "Hello";
string s = obj as string;  // ✅

## Q5 : Agar as operator se cast karna ho aur type match na kare toh kya hoga?
Ans : Exception nahi aayega, value null ho jayegi.

## Q6 : Agar is operator use karke cast karna ho toh kaise karoge?
Ans : Pattern matching ke saath.
if (obj is string str)
{
    Console.WriteLine(str);
}

## Q7 : Boxing/unboxing me casting kaise involved hai?
Ans : 
Value type → object (Boxing)
object → value type (Unboxing → explicit casting required)

int x = 100;
object obj = x;      // boxing
int y = (int)obj;    // unboxing

## Q8 : Explicit cast aur Convert class me kya difference hai?
Ans : 
- Explicit cast exception throw karega agar fail ho gaya.
- Convert class safe hai, mostly null/invalid ko handle kar leta hai (default value return karke).

## Q9 : Performance me as aur direct cast me kya difference hai?
Ans : as ek hi baar type check karta hai. Direct cast ((string)obj) type check + cast dono karta hai → thoda slow.

## Q10 : Agar tum ek base class object ko derived class me cast karte ho aur wo valid nahi hai toh kya hoga?
Ans : Direct cast pe → InvalidCastException.
as operator pe → null.

## Q11 : Trading system me tumhe ek object milta hai jisme kabhi int price aata hai aur kabhi string price aata hai. Tum kaise handle karoge?
Ans : is / as use karke safe cast karunga.

## Q12 : Agar tumhe ek User object hai aur tum check karna chahte ho ki wo Admin type ka hai ya nahi, toh kya karoge?
Ans : 
if (user is Admin adminUser)
{
    adminUser.ApproveOrder();
}

## Q13 : Agar tumhe ek API se object aata hai jiska type run-time pe decide hota hai, toh kis casting ka use karoge?
Ans : dynamic ya as, safe handling ke liye.

## Q14 : Agar tumhe ek DB column ka value aata hai jo DBNull bhi ho sakta hai, toh kis method se safe conversion karoge?
Ans : Convert.ToInt32() ya as int?

# 6. Strings → Immutable, StringBuilder, intern pool.
## Basics
- Strings are Immutable
C# me string ek reference type hai , but immutable hoti hai -> ek baar create ho gayi toh chnage nahi hoti.

string s1 = "Amit";
s1 = s1 + " Gupta";  // new string banegi

Strings are immutable in C#, means every modification creates a new object in memory.

- StringBuilder (Mutable Alternative) 
Jab tumhe bahut zayada modification karna hote hain(loop , append , replace, remove) , toh string builder use karte hain.
Few modifications → string is fine.
Heavy modifications → use StringBuilder.

- String Intern Pool
String intern pool is a performance optimization in C# where identical string literals share the same memory reference.

## Q1 : String is value type or reference type in C#?
Ans : Reference type hai, but behaves like value in some scenarios (immutable hone ke wajah se).

## Q2 :  Why are strings immutable in C#?
Ans : 
1. Security (passwords, config values safe rakhne ke liye)
2. Thread-safety (multi-thread apps me safe)
3. Interning optimization possible hota hai

## Q3 : Difference between string and System.String?
Ans : string = C# alias, System.String = actual .NET class. Dono same hai.

## Q4 : How to compare two strings in C#?
Ans :
1.  == → content compare karta hai
2. .Equals() → safe, overloads bhi available
3. String.Compare(a,b,true) → case-insensitive comparison

## Q5 : How is string stored in memory?
Ans : Heap me store hoti hai (kyunki reference type hai). String literals intern pool me aa jate hain.

## Q6 : What is String Interning?
Ans : Optimization jisme same literals ek hi memory block use karte hain.

## Q7 : How do you force a string into intern pool?
Ans : String.Intern(str);

## Q8 : Difference between string and StringBuilder?
Ans : String immutable, har modification new object banata hai. , tringBuilder mutable, ek hi object modify hota hai.

## Q9 : When should you use StringBuilder?
Ans : Jab loop me 100s-1000s concatenations karni ho.

## Q10 : Is string thread-safe in C#?
Ans : Haan, kyunki immutable hai → ek thread change kare toh bhi doosre thread ka effect nahi hoga.

## Q11 : What is the difference between ==, .Equals(), and ReferenceEquals() for strings?
Ans : == → content compare karta hai
      .Equals() → content compare karta hai
      ReferenceEquals() → reference compare karta hai (intern pool hone pe true aasakta hai).

## Q12 : How to make string case-insensitive compare?
Ans : String.Equals(a, b, StringComparison.OrdinalIgnoreCase)

## Q13 : Can string be null or empty? Difference?
Ans : 
- null → object hi nahi bana
- "" → object bana but empty hai
- String.IsNullOrEmpty(str) → dono check karne ka shortcut

## Q14 : What is String.Join() vs String.Concat()?
Ans : 
- Concat() → bina separator join karega
- Join() → tum separator de sakte ho ("," ya "|")

## Q15 : How does garbage collector handle strings?
Ans : Strings intern pool me ho toh GC free nahi karega, but dynamically banayi gayi string GC ke through free ho jayegi agar reference nahi hai.

## Q16 : Difference between string.Copy() , String.Clone() ,String.Intern()?
Ans : 
- Copy() -> ek nayi copy deta hai(but deprecated).
- Clone() -> shallow copy deta hai (basically reference return karta hai).
- Intern() -> string ko intern pool me daal deta hai.

## Q17 : What is string interpolation and how is it different from String.Format() ?
Ans : 
- Interpolation → $"Hello {name}" (readable + compile-time checked).
- String.Format -> String.Format("Hello {0}",name) (runtime binding).

## Q18. What is verbatim string literal in C#?
Ans :
@"C:\Users\Amit" -> escape sequences ignore hote hain.

## Q19 : Performance wise difference between concatenation (+), String.Concat, StringBuilder?
Ans : 
- Few concats → + fine hai (compiler optimize kar deta hai).
- Multiple concats → String.Concat better.
- Loops → StringBuilder best.

## Q20 :  Can you make your own immutable class like string?
Ans : Haan, by making fields readonly and not exposing setters.

