# Basics ASP.NET Core Questions
## Q1 : What is Asp.Net Core?
Ans : ASP.NET Core ek web Framework hai jiska use hum Websites, Web APIs, Aur applications banane ke liya karte hair. Ye .NET ka naya Version hai jo Windows, macOS , aur Linux sab pe Kaam Kasta hai.

-> IS KA UE KYU KAREIN?
1. Fast and High Performace : Buth Fast Run Hota hai.
2. Cross - PlatForm : Windows ke alawa Mac aur Linux e bi aam kata hai.
3. Open Source : Free hai , app code dekh sakte ho , modfy bhi kar sakte ho.
4. Cloud Ready : Azure jaise cloud platforms ke liye optimized hai.
5. Modular Architecture : Aapko sirf wahi libraries add karni hoti hain jo aapko chahiye.

-> ASP.NET Core me kya ban sakta hai?
1. Websites (front-End + Back-End)
2. REST APIs (for mobile/web apps)
3. Real time (using SignalR)
4. Microservices
5. BlaZor Apps (C# based Web UI)

## Q2 : What are the features of Asp.Net Core?
Ans : Features : 
1. Cross - Platform Support 
-> Aap ASP.NET Core apps Windows, Linux , MacOS sab pe chala skte ho.
-> Ek hi Code har OS pe kam karega.

2. High Performance :
-> ASP.NET Core is one of the fastest web frameworks.
-> Optimized for speed and low memory usage.

3. Open Source and Community Driven 
-> Ye GitHub pa Available hai. Free to use and improve.
-> Microsoft + Community milke maintain karta hain,

4. Modular and Light Weight
-> App only required packages ko use kar skate ho.
-> No extra bloat = faster and cleaner app.

5. Dependecy Injection (DI) Built In.
-> DI directly framework me built - in hai.
-> Code maintain karna aur test karna easy hota hai.

6. Unified MVC and Web API
-> MVC (Model-View-Controller) aur Web API ka single programming model.
-> Alag-alag code likhne ki zarurat nahi.

7. Razor Pages  
-> Razor Pages allow simpler and Cleaner code for UI.
-> Begineer - Friendly and good for page based apps.

8. Asynchronous Programming with async/await
-> ASP.NET Core fully supports async programming.
-> Scalable apps banane ke liye zaroori hai.

9. Integrated with Modern Front-End Frameworks
-> Angular, React, Blazor, etc. ke saath easily integrate ho sakta hai.
-> Modern SPA (Single Page Applications) bana sakte ho.

10. Built-in Middleware Pipeline
-> Middleware components like authentication, logging, error handling easily add ho jaate hain.
-> Control every request & response.

11. Cloud-Ready Configuration and Deployment
-> Easily deployable to cloud platforms like Microsoft Azure, AWS.
-> Environment-specific configuration bhi supported hai.

## Q3 :  What are the advantages of ASP.NET Core over ASP.NET (.NET Framework)?
Ans : 
1 . Cross Platform : Core Windows, Linux, MacOS pa run kr skta ha , jabki ASP.NET Sirf Windows pe chalta hai.
2. Core lightweight aur high performace framwork hai  ,Kyu ki ya kresteral server use krta ha jo buth fast ha,
3. Core Open Source hai, to community bhi contribute karti ha.
4. Core ma build in dependency Injection support hota hai , jo code ko maintain karna and test karna easy bananta ha,
5. Unified programming model hai MVC aur Web API alag nahi hai , same tarike se handle kiya jata hai,
6. App Self hosting be kr skta ho.
7. Sab sa important this is clound ready, specially For Azure.

"To Overall, ASP.NET CORE modern ,Fast, aur scalable application banata ke liya best choice hai -  especially jab aapko perfornace, flcecibility aur cloud - depoloyment chahiya ho."

## Q4 : What is Asp.Net Core meta package?
And  : ASP.NET Core meta package ek combined NuGet packages tha jisme ASP.NET Core ki commonly used libraries budled hoti thi - 
jise hum ek hi line me install kar lete the , instead of adding multiple packages individually.

Ye package "Microsoft.AspNetCore.All" ke naam se aata tha .NET Core 2.0 me , aur baad me "Microsift.AspNetCore.App" me Convert ho gaya .NET Core 2.1 ka baad.

Iska fayda ya tha ki hume manually har package ka version manage nahi karna padta tha - sab compatible version automatically mil jata tha.

1. Microsoft.AspNetcore.All (used in .NET Core 2.0) : 
    Isme runtime unused libraries bhi hoti thi, Isliya thoda heavy tha.

2. Microsift.AspNetCore.App(from .NetCore 2.1) : 
    Isme sirf runtime libraries hoti hain jo actually use hoti hain.
    Self - Contained deployment ke liya optimize kiya gaya.
    EG: Microsift.AspNetCore.App meta package automatically include kate hai : Razor, MVC , SignalR , Identity , EntityFramework.
    MAnually sab package install krna ki jarror nahi.

"ASP.NET Core MEta PAckage ek Convenient way tha multiple related packages ko ek hi dependency me include karne ka - taaki version conflicts na ho aur development faster jo jaye."

## Q5 :  When do you choose classic ASP.NET MVC over ASP.NET Core?
Ans : 
1. The Exisiting application is already built on ASP.NET MVC and full migration is not feasible due to time , cost ,or risk.

2. The project requires third-party libraries or legacy systems that are compatible only with the .NET Framework.

3. The target hosting environment is strictly Windows-only — for example, internal enterprise apps on Windows Server with IIS.

4. The team or client is not ready to move to the newer ecosystem yet, due to maintenance or skill-set limitations."

## Q6 : What is a web application framework, and what are its benefits?
Ans : "A Web Application Framework ek software platform hota hai jo web applications develop karne ke liya toos , libraries , aur structure provide karta hai.
Iska main goal hai developement ko faster , easier , aur more secure banana - without writing everything from scratch."

Key Benefits :
1. Faster Development:
➤ Reusable components aur built-in tools ki wajah se development speed badhti hai.
2. Code Reusability & Structure:
➤ Frameworks (jaise MVC) project ko structured rakhte hain — easy to manage & scale.
3. Security Features:
➤ SQL injection, XSS, CSRF jaise attacks ke against built-in protection dete hain.
4. Routing System:
➤ URLs easily handle karne ke liye route mapping hota hai.
5. Built-in Support for Databases & Sessions:
➤ ORM tools aur session management already included hote hain.
6. Testing Support:
➤ Unit testing aur integration testing ke tools integrated hote hain.
7. Community & Support:
➤ Popular frameworks ka large community hota hai — help milti rehti hai.


# Basics Servers ,Application Starting 
## Q1 : What is Kestrel and what are advantages of Kestrel in Asp.Net Core?
Ans : Kestrel is the default cross platform web server used in ASP.NET Core.
It is a lightweight, high-performance server that handles HTTP requests and can run independently or behind other web servers like IIS, Nginx, or Apache.

->  Advantages of Kestrel in ASP.NET Core
1. Cross Platform : Works On Windows, Linux , MacOS
2. Hight Performace : It's one of the fastest web servers, build on libuv (earlier) and now Sockets API for better speed.
3. Lightweight and Minimal Overhead : Kestrel has low memory usage and minimal features by default, making it faster and scalable.
4. Self Hosting Support : Can work standalone.
5. Reverse Proxy Friendly : Can used behinf IIS , Nginx , Apache

## Q2 : What is the difference between IIS and Kestrel? Why do we need two web servers?
Ans : IIS and KEsteral dono WebServer hain , lekin dono ka role and Usage Thoda different ha..

1. Kestrel is Cross platform , while IIS is window only
2. Kestrel is Lightweight  high perforamce  webserver ,while IIS is fully featured enterprice -grade web server 
3. Kestrel asp.net core  directly rn krna ka liya, while IIS is for production hosting, reverse proxy, security layer.
4. Kestrel can be used alone in development /test environment, while IIS ot commontly used alone with Core apps.

"Kestrel high performace deta hai, lekin usme advance features nahi hote - jaise SSL termination, request filtering , Window authentication, etc.

Isliya production me hum Kestrel ko behind IIS ya Nginx use kaste hain as a reverse proxy."

## Q3 : What is the purpose of launchSettings.json in asp.net core?
Ans : "launchSettings.json ek configuration file hoti hai jo ASP.NET Core application ke run time settings define karti hai - specially during development"

Purpose of launchsettings.Json
1. App kounse URL pe run karega.
2. Kaunsa environment (Developemnt, Staging , Production) use Hoga.
3. Kis Web Server (Kestrel , IIS Express) ke throuhg app chalega,
4. Agar debugging ya launch ke time pe command line argument dnen ho, wo bhi yahan define hote hain.
```json
{
  "profiles": {
    "IIS Express": {
      "commandName": "IISExpress",
      "launchBrowser": true,
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    },
    "MyAspNetCoreApp": {
      "commandName": "Project",
      "launchBrowser": true,
      "applicationUrl": "https://localhost:5001;http://localhost:5000",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    }
  }
}
```
"Is Short, launchSettings.json" development ke time app ke behaviour ko control karta hi - jisse debugging aur testing easy ho jati ha.

## Q4 : What is generic host or HostBuilder in .NET Core?.
Ans : "Generic Host ya HostBuilder ek central Object hai jo .NET Core Application ka Lifecycle manage karta hai - Including dependency injection, configuration , logging, background services etc."

ye host app ke liya ek runtime environment banata hai

-> Use of Generic Host :
Aphe ka ASP.NET Core app , background service , console app  sab HostBuilder ke through configure kiya ja sakta hai.

-> What Does HostBilder configure?
1. App Configuration(from appsettings.json, evn vars, CLI args)
2. Dependency Injection Container
3. Logging
4. Services(Hosted Services , Middelware)
5. Environment Variables(Development, Production etc.)

## Q5 : What is the purpose of the .csproj file?
Ans : ".csproj file ek XML based file hoti hai jo .NET project ki configuration, dependencies , build instructons, aur metadata define karti hai.
Ye Visual Studio ya dotnet CLI ko banata hai ki project kaise build aur run karna hai."

-> Main Purpose of .csproj File : 
1. Target framework specify karna(.NET Core , .NET 6 ,.NET Framework)
<TargetFramework>net6.0</TargetFramework>
2. NuGet packages dependencies define karna
<PackageReference Include="Newtonsoft.Json" Version="13.0.1" />
3. Project Type Set karna(Web app,class library, console app)
4. Build settings manage karna(output path, warnings, compiler options)
5. Project reference aur file inculdes/Exculdes control karna(linked projects, or folders)

```
$$
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net6.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="6.0.0" />
  </ItemGroup>

</Project>
$$
```
"In short, .csproj file project ka blueprint hota hai — jo .NET build tools ko batata hai ki project ko kaise compile, restore, aur run karna hai."

"Sir, jab bhi .NET project build ya run hota hai, sabse pehle .csproj file read hoti hai — isme hi define hota hai project ka behavior, dependencies, framework, aur output type."

## Q6 : What is IIS?
Ans : "IIS (Internet Information Services) ek web server software hai developed by Microsoft.

Ye web applications ko host karne, manage karne, aur serve karne ke liye use hota hai — specially ASP.NET, static files, REST APIs, etc."

Some Features:
1. Web Hosting : IIS HTTP requests receive karta hai aur corresponding response send karta hai.
2. Application Pool Management : Different apps ko isolate karne ke liye app pools create karta hai for better security and performance.
3. Request Handling : URLs ko route karta hai to correct application (ASP.NET, PHP, static HTML, etc.)
4. Sercuity : Built-in support for Windows Authentication, SSL, request filtering, and authorization rules.
5. Logging and Monitoring : Access logs, error logs, performance counters
6. Module Support : Caching, Compressing , static file serving

## Q7 : What is the “Startup” class in ASP.NET core prior to Asp.Net Core 6?
Ans : "Startup Class ASP.NET Core app ka entry point hoti thi(before .NET 6), jahan pe app applications ka configuration aur request pipeline define karte the
Ye class batati thi app me kaunse services register karne hain, aur HTTP requests ko kaise handle karna hai."

It has two Method : 
1. ConfigureServices : Service regster karne ka liya.
2. Configure :  Middleware setup karne ka liiya (HTTP request pipeline)

"So in short, before .NET 6, the Startup class was the heart of configuration in ASP.NET Core apps, where all services and request handling logic were defined."

"Later All the start up logic moved into single file Program.cs and no need for two separate method"

## Q8 :  What does WebApplication.CreateBuilder() do?
Ans : 
1. Configure the app to use Kestrel as web server.
2. Specify to use the current project directory as root directory for the application.
3. Setup the configuration sub-system to read setting from appsettings.json and appsettings.{env}.json to environment specific configuration.
4. Set Local user secrets storage only for the development environment.
5. Configure environment variables to allow for server-specific settings
6. Configure command line arguments (if any).
7. Configure integration with IIS
8. Configure the default service provider.

# HTTP Basics
## Q1 : What is HTTP?
Ans : "HTTP ka Full form hai HyperText Transfer Protocol.
Ye Ek Communication protocol hai jo web browsers aur web servers ke beech data exchnage karne ke liya ue hota hai."

Jab bhi aap browser me koi website open karte ho — for example, https://www.google.com —

To browser ek HTTP request bhejta hai server ko, aur server ek HTTP response return karta hai with HTML, CSS, JSON ya koi aur data.

-> Features of HTTP :
1. Stateless :  Har request independent hoti hai (server previous request ya session yaad nahi rakhta by default)
2. Text-based protocol: Human-readable requests/responses
3. Works on Port 80 (HTTP) / 443 (HTTPS)

-> What is HTTPS?
HTTPS = HTTP + SSL (Security)
It encrypts the communication between client and server for safety.

## Q2 : What is the format of a Request Message?
Ans : 
Request Headers

"HTTP Request Message ek specific format follow karta hai jisme client (browser) server se koi resource (like web page, data) maangta hai.
Is format me 3 main parts hote hain:"

1. Request Line :  ye batata hai : 
-> Kaunsi method use ho rahi hai (GET ,POST, etc)
-> Kaunsi resource chahiye
-> Kaunsi HTTP version hai.

Example : GET /index.html HTTP/1.1

2. Headers :Extra Inf0 dete hain server ko (Like  browser type, host name , accepted formats etc)

Example
Host : www.example.com
User-Agent : Mozilla/5.0
Accept : text/html

3. Body (Optional) :
Sirf kuch methods (like POST, PUT) ke liye use hota hai
Isme data hota hai jo client server ko bhejna chahta hai (e.g. form data, JSON)

Example : name=John&age=25

"Toh HTTP Request message teen parts me divided hota hai — Request Line, Headers, aur Body — jiske through client server se specific data ya action perform karne ka request bhejta hai."

Response Headers
1. Status Line:
HTTP Version + Status Code + Message

HTTP/1.1 200 OK

2.Headers:
Server info, content type, caching

Content-Type: text/html  
Content-Length: 1024  

3. Body:
Actual data (HTML, JSON, image, etc.)

css
Copy code
<html>
  <body>Hello, User!</body>
</html>

## Q3 : What are the important HTTP methods (or HTTP verbs) – (GET, POST, PUT, PATCH, HEAD, DELETE)?
Ans : 
1. GET : 
  Purpose - Server se data/feth karna
  Used For - Browser pages, API reads
  Note - Safe, No Body, No data modification

  Example : GET /products HTTP/1.1

2. POST :
  Purpose - Server pe naya data create karna
  Used For - Form Submissions, Registeration, Login
  Body Required - Yes

  Example : POST /users  
  Body: { "name": "Rahul", "email": "r@x.com" }

3. PUT :
  Purpose - Existing data ko replace/update karna
  Used For - Updating full object
  Body Required : Yes(replaces entire resource)

  Example : PUT /users/101  
  Body: { "name": "Updated Rahul", "email": "r@x.com" }

4. PATCH : 
  Purpose: Partial update karna (only kuch fields)
  Used For: Updating specific fields only
  Body Required: Yes

  Example : PATCH/users/101
  Body : { "email" : "new@x.com" }

5. DELETE :
  Purpose: Resource delete karna
  Used For: Deleting user, product, post etc.

  Example: DELETE /users/101

6. HEAD :
  Purpose : Only headers fetch karta hai — body nahi
  Used For : Check if resources exisits, without downloading

  Example : HEAD /products

## Q4 : What are the important HTTP status codes?
Ans : 
1xx - Informational
Code	Meaning	  Use Case
100	  Continue	Request ka initial part OK hai

2xx - Success
Code	Meaning	    Hindi Description
200	  OK	        Request sahi thi, aur response mil gaya
201	  Created	    Naya resource successfully create ho gaya
204	  No Content	Request OK hai, but koi content nahi bhejna

3xx -  Redirection
Code	Meaning	      Hindi Description
301	  Moved         Permanently	Resource ka naya URL fix ho gaya hai
302	  Found	        Temporarily new location
304	  Not Modified	Cache se hi use karo, server ne kuch change nahi kiya

4xx - Client Error
Code	Meaning	            Hindi Description
400	  Bad                 Request	Request me kuch galti hai (invalid data etc.)
401	  Unauthorized	      Authentication required (login missing)
403	  Forbidden	          Access mana kiya gaya hai (unauthorized access)
404	  Not Found	          Resource ya page nahi mila
405	  Method Not Allowed	Server is HTTP method ko allow nahi karta

5xx - Server Error
Code	Meaning	                Hindi Description
500	  Internal Server Error	  Server crash ya unexpected error
502	  Bad Gateway	            Server ne galat response diya
503	  Service Unavailable	    Server down ya busy hai
504	  Gateway Timeout	        Server ne time par response nahi diya

Important : 200,201,400,401,403,404,500 

## Q5 :  What is Content Negotiation in HTTP?
Ans : You go to a restaurant (server) and say to the waiter:

“Mujhe menu Hindi me chahiye.”
(Accept: Hindi)

If the restaurant has a Hindi menu, they give it to you.
If not, they may say:

“Sorry sir, sirf English menu available hai.”
(Fallback content)

"Content Negotiation bilkul us situation jaise hota hai jahan customer waiter ko batata hai ki wo kaunsi language me menu chahata hai — aur waiter uske according menu provide karta hai. HTTP me, client Accept header ke through yeh batata hai, aur server uske hisaab se best format me response bhejta hai."

## Q6 : Explain how HTTP protocol works?
Ans : HTTP (HyperText Transfer Protocol) ek stateless protocol hai jo client (browser) aur server ke beech data exchange ke liye use hota hai — mostly web pages, APIs, images, etc.

-> How HTTP Works – Step-by-Step
- Step 1: Client Sends a Request
GET /index.html HTTP/1.1  
Host: www.example.com

- Step 2: Server Processes the Request
Server (like IIS, Apache, or Kestrel) receives the request, finds the resource, processes logic, etc.

- Step 3: Server Sends a Response
HTTP/1.1 200 OK  
Content-Type: text/html  

<html>Welcome</html>

- Step 4: Client Displays the Data
 Browser shows the result to the user — webpage, JSON, image, etc.

-> Real-Life Analogy:
1. You (client): Order karte ho (request)
2. Waiter (HTTP protocol): Order convey karta hai
3. Kitchen (server): Khana banata hai
4. Waiter wapas lataa hai (response)

"HTTP ek request-response protocol hai jisme client server se resources maangta hai aur server appropriate format me response karta hai — yeh web communication ka foundation hai."

## Q7 : What is WebServer?
Ans : "Web server ka kaam hai client se request lena, uska response prepare karna, aur appropriate web content wapas bhejna — yeh pura communication HTTP protocol ke through hota hai."

# Middleware
## Q1 : What is middleware ?
Ans : Middleware ek software component ha /Code block ha , jo request and response ke beech kaam karta hai - jaise logging , authentication , routing , error handling etc.

Example : Socho app airport par ja rha ho "
Aapko check in , security , immigration, boarding - sabse sa guzarna padtha hai.
Each step is like a middelware - input leta hai, kush process karta hai, aur aaga bhejta hai.

-> HOW MIDDLEWARE WORKS
1. Client se HTTP Request aata hai
2. Har Midleware us request ko check karta hai
3. Agar zarurat ho to response bhi wahi se bhej sakta hai
4. Warna request ko next middleware ko pass karta hai.

```c#
app.Use(async (context, next) =>
    {
        Console.WriteLine("Middleware 1: Before");
        await next(); // Passes to next middleware
        Console.WriteLine("Middleware 1: After");
    });
```
Common Middleware : 
1. UseRouting() - URL ke basis par route decide karta hai
2. UseAuthentication() - User authentication handle karta hai
3. UseAuthorization() - User ke rights check karta hai
4. UseEndpoints() - Endpoint ko execute karta hai
5. UseStaticFiles() - Static HTML/CSS/JS files serve karta hai

"Middleware ek tarah ka step-by-step processing layer hota hai HTTP pipeline me — jo request ko modify, handle ya forward karta hai — ASP.NET Core me yeh highly flexible aur powerful hai."

## Q2 : What is the difference between IApplicationBuilder.Use() and IApplicationBuilder.Run()?
Ans : 
1. Use() - Middleware Chain Banata Hai
Use() middleware ko next middleware ke pass request forward karne ki ability hoti hai.
It calls the next middleware in the pipeline using await next().
```c#
app.Use(async (context, next) =>
{
    Console.WriteLine("Before");
    await next(); // next middleware ko call karta hai
    Console.WriteLine("After");
});
```

2. Run() – Last Middleware Hoti Hai
Run() ek terminal middleware hoti hai – yeh request ko yahin khatam kar deti hai.
It does NOT call next(), so koi middleware uske baad execute nahi hota.
```c#
app.Run(async (context) =>
{
    await context.Response.WriteAsync("This ends the pipeline");
});
```

## Q3 : What is the use of the "Map" extension while adding middleware to the ASP.NET Core pipeline?
Ans : "Map() ka use tab hota hai jab aap specific path ke liya alag middleware chain banana chahte ho."

-> Why Use Map()?
1. To create conditional routes in the middleware pipeline
2. Helps you organize logic based on paths like /admin, /api, etc.
3. Keeps the main pipeline clean and modular

```c#
app.Map("/admin", adminApp =>
{
    adminApp.Run(async context =>
    {
        await context.Response.WriteAsync("Welcome to Admin Area");
    });
});

app.Run(async context =>
{
    await context.Response.WriteAsync("Welcome to Main Site");
});
```
URL: /admin → Response: "Welcome to Admin Area"

URL: / or anything else → "Welcome to Main Site"

-> Real Life Analogy :
Imagine a traffic signal junaction :
If you go left(/admin) -> admin here
IF you go Straight -> normal lane
Map() is like setting path-specific lanes in the traffic flow.

"Map() ASP.NET Core me ek middleware branching technique hai jo specific URL path ke liye alag pipeline define karta hai – jaise /admin, /api ke liye custom logic."


## Q4 : How do you create a custom middleware?
Ans : The custom middleware class can be used to separate the middleware code from the Program.cs (or Startup.cs in earlier versions).

You can create a custom middleware either by implementing IMiddleware interface or by using convention middleware

1. Implementing IMiddleware:

```c#
public class MyCustomMiddleware : IMiddleware
{
 public async Task InvokeAsync(HttpContext context, RequestDelegate next)
 {
  //TO DO: before logic
  await next(context);
  //TO DO: after logic
 }
}
```
2. Convention Middleware:
```c#
public class MyCustomMiddleware
{
 private readonly RequestDelegate _next:
 public MiddlewareClassName(RequestDeletegate next)
 {
 }

 public async Task InvokeAsync(HttpContext context)
 {
  //TO DO: before logic
  await _next(context);
  //TO DO: after logic
 }
}
```

## Q5 : What is the right order of middleware used in production-level applications?
Ans : 
```c#
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    // 1. Exception Handling
    if (env.IsDevelopment())
        app.UseDeveloperExceptionPage();
    else
        app.UseExceptionHandler("/Home/Error");
    
    // 2. HTTPS Redirection
    app.UseHttpsRedirection();

    // 3. Static Files (wwwroot)
    app.UseStaticFiles();

    // 4. Routing
    app.UseRouting();

    // 5. CORS (if using APIs)
    app.UseCors();

    // 6. Authentication
    app.UseAuthentication();

    // 7. Authorization
    app.UseAuthorization();

    // 8. Endpoints (MVC, Razor, or API)
    app.UseEndpoints(endpoints =>
    {
        endpoints.MapControllerRoute(
            name: "default",
            pattern: "{controller=Home}/{action=Index}/{id?}");
    });
}
```
Step	Middleware	        Purpose (Hindi Explanation)
1	    Exception Handling	Errors ko gracefully handle karta hai
2	    HTTPS Redirection	  HTTP requests ko HTTPS me convert karta hai
3	    Static Files	      HTML, CSS, JS files serve karta hai bina controller ke
4	    Routing	            Request ko route mapping se match karta hai
5	    CORS (optional)	    Cross-Origin requests allow/deny karta hai
6	    Authentication	    User ki identity verify karta hai
7	    Authorization	      User ke rights check karta hai
8	    Endpoints	          Final response controller ya API se aata hai

# Routing
## Q1 : What is Routing?
Ans : Routing ka matlab hai - jab ek HTTP request serer pe aati hai , to kaunsa controller aur kaunsi action method us request ko handle karegi , yeh decide karna.

-> Why Routing Needed ?
To handle different URLs and map them to :
1. Controller Actios
2. Razor Pahes
3. API EndPoints

Types : 
1. Conventional Routing  :  Uses predefined URL Patterns
```c#
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
});
```

2.  Attribute Routing : Uses attributes directly on controllers
```c#
[Route("products")]
public class ProductsController : Controller
{
    [Route("details/{id}")]
    public IActionResult Details(int id) { ... }
}
```
-> Real-Life Analogy:
Socho ek mall me ja rahe ho. Har shop ke saamne ek board laga hai (URL). Routing decide karta hai ki kaunsi shop (controller/action) me aapki request jayegi.

"Routing ASP.NET Core me request ko sahi controller aur action method tak le jane ka mechanism hai — yeh URL pattern ke basis pe kaam karta hai."

## Q2 : How Routing works in ASP.NET Core?
Ans : "Jab ek HTTP request aati hai, routing decide karti hai ki kaunsa controller/action ya endpoint usse handle karega."

-> How It Works – Step by Step:
1. App Starts -> Middleware Pipeline is configured.
2. UseRouting() is called to enable Routing.
3. UseEndPoints() defines the routes
4. When a request comes : 
    a. Routing parses the URLS
    b. It matches the URLS to a Defiend route
    c. It inokes the matched controller/action.

## Q3 : What are the important route constraints?
Ans : In ASP.NET Core, route constraints are used to restrict the values that can be matched for route parameters. They are an essential part of defining more specific and controlled routes. Here are some important route constraints you can use:

int: Constrains the parameter to be an integer.

long: Constrains the parameter to be a long integer.

bool: Constrains the parameter to be a Boolean value, i.e., "true" or "false".

double: Constrains the parameter to be a double-precision floating-point number.

float: Constrains the parameter to be a floating-point number.

guid: Constrains the parameter to be a GUID (Globally Unique Identifier).

datetime: Constrains the parameter to be a valid date and time value.

alpha: Constrains the parameter to contain only letters (no digits or special characters).

regex: Allows you to define a custom constraint using a regular expression pattern.

length: Constrains the parameter to have a specific length. For example, {id:length(5)} will only match when the id parameter has a length of 5 characters.

min and max: Allows you to specify minimum and maximum values for numeric parameters. For example, {age:min(18)} will only match if the age parameter is 18 or greater.

range: Similar to min and max, but allows you to specify a range of values. For example, {year:range(1900, 2023)} will only match if the year parameter is between 1900 and 2023.

required: Indicates that the parameter is required and must be present in the URL for the route to match.

nonempty: Ensures that the parameter is not empty (not null, empty string, or whitespace).

maxlength and minlength: Restricts the length of a string parameter. For example, {username:maxlength(20)} will only match if the username parameter has a length of 20 characters or less.

## Q4 : What is the purpose of the wwwroot folder?
Ans : The wwwroot folder is a special folder in an ASP.NET Core web application that serves as the web root. Its purpose is to store static files, such as HTML, CSS, JavaScript, images, and other client-side assets that need to be directly accessible by the web browser.

When a web application receives a request, the web server looks for the requested resource within the wwwroot folder. If the resource is found in this folder, the web server serves it directly to the client without involving the ASP.NET Core middleware pipeline.

## Q5 : How do you change the path of wwwroot folder?
Ans : We need to set path of the wwwroot folder in the WebRootPath propertyof the WebApplicationOptions class.

```c#
var builder = WebApplication.CreateBuilder(new WebApplicationOptions() {
 WebRootPath = "foldername"
});
```

# Controllers 
## Q1 : What is Controller?
Ans : "Controller ek aisi class hoti hai jo clinet se aayi request ko handle karti hai, processing karti hai aur ek proper response return karti hai - jaise ek View ya JSON."

-> How Does It Work
1. URL ke through controller call hota hai
2. Controller -> Service ->Data fetch
3. Controller -> View ya JSON  return karta hai

-> Controllers Folder Structure :
1. Normally placed in controllers/folder
2. Class name ends with Controller
3. Inherits from Controller base class

-> Real Life Analogy : 
Socho ek restaurant manager hai (controller).
Customer (user) order deta hai → manager (controller) kitchen (service/model) se kaam karwata hai → final dish (view/JSON) table pe bhejta hai.

-> Summary :
srno  Feature         Controller  
1     Role            Handles HTTP request
2     Returns         HTML View, JSON etc
3     Inherits From   Controller class
4     Part of         MVC (Model View Controller)

-> Interview One Liner
"Controller ASP.NET Core MVC ka central part hai jo client ki request ko handle karta hai, process karta hai aur appropriate response bhejta hai — jaise View ya JSON."

## Q2 : What is an Action Method?
Ans : "Action Method is a pulic method inside a controller that handles HTTP requests (like GET  POST) and returns a response (like View, JSON , File ,etc)."

-> Key Points
srno  Point                         Explanation
1     Must be public                Private methods cannot be action methods
2     Can return IActionResult      Like View, Json, Redirect, etc.
3     One Controller = Many Actions Controller can have multiple action methods

-> Interview One - Liner
"Action method ek controller ke andar likhi hui public method hoti hai jo user request ko handle karke appropriate response (jaise View ya JSON) return karti hai."

## Q3 : Explain different types of Action Results in asp.net core?
Ans : Controller is a class that is used to group up a set of action methods.
1. IActionResult : Defines a contract that represents the result of an action method.
2. Action Result : A default implementation of IActionResult.
3. ContentResult : Represents a text result.
4. EmptyResult : Represents an ActionResult that when executed will do nothing.
5. JsonResult : An action result which formats the given object as JSON.
6. PartialViewResult : Represents an ActionResult that renders a partial view to the response.
7. ViewResult : Represents an ActionResult that renders a view to the response.
8. ViewComponentResult : An IActionResult which renders a view component to the response.
9. StatusCodeResult : An IActionResult which sends a specific HTTP status code in response, without any response body.
10. UnauthorizedResult : An IActionResult which sends HTTP 401 status code in response, with / without any response body.
11. BadRequestResult : An IActionResult which sends HTTP 400 status code in response, with / without any response body.
12. NotFoundResult : An IActionResult which sends HTTP 404 status code in response, with / without any response body.
13. ObjectResult : An IActionResult which sends the data of the specified object in response body.
14. FileResult : An IActionResult which sends content of the specified file in response body.
15. RedirectToActionResult : An IActionResult which sends HTTP 301 or 302 status code in response to redirect the request to the specific action method.
16. LocalRedirectResult : An IActionResult which sends HTTP 301 or 302 status code in response to redirect the request to the specified local URL (within the same domain).
17. RedirectResult : An IActionResult which sends HTTP 301 or 302 status code in response to redirect the request to the specified local URL (within the same domain) or an external URL.

## Q4 : What’s the HttpContext object? How can you access it within a Controller?
Ans : "HttpContext ek aisa object hota hai jo ek HTTP request ke baare me poora context (jaise request headers, cookies, session, user info) deta hai."

-> HttpContext Includes
srno  Property       Use
1     Request        Incoming request info (headers, body, query)         
2     Response       Outgoing response (status, headers) 
3     Session        Stores user session data
4     User           Current authenticated user info
5     Items          Store data during one request
6     Connection     IP address, connection details
7     Cookies        Access browser cookies

-> Real Life Analogy :
"Socho ek courier package aaye- uske saat packet info , sender info , reciever info sab kust aata hai.
Waise hi , Http Context ka paas request aur reqponse ki saari details hoti hain."

-> How to Access HttpContext in a Controller
ASP.NET Core controllers automatically get HttpContext via the base Controller class.

-> Interview One Liner
"HttpContext ASP.NET Core ka object hai jo har HTTP request aur response ka complete detail rakhta hai — controller ke andar ise directly use kiya ja sakta hai for accessing request, response, session, user etc."

# Models Binding and Validations
## Q1 : What is model binding in ASP.NET CORE?
Ans : "Model Binding ek asia feature hai jo request data ko automatically C# varibales ya objects me convert kar deta hai - aapko manually parse karne ki zarurat nahi hoti."

-> Example :
Example 1 : Simple Parameters (Query String)

URL : /Product/Details?id=5&name=Phone

Controller : 
```c#
public IActionResult Details(int id, string name)
{
    // id = 5, name = "Phone" -- automatically bound
    return Content($"Product ID: {id}, Name: {name}");
}
```
Example 2 : Binding to a Model Class

Class :
```c#
public class UserModel
{
    public string Name { get; set; }
    public int Age { get; set; }
}
```
Controller : 
```c#
[HttpPost]
public IActionResult Save(UserModel user)
{
    // Automatically binds form or JSON data to UserModel
    return Content($"Name: {user.Name}, Age: {user.Age}");
}
```
-> Where odel Binding Can Read From :
Srno    Source            Example
1       Route Value       /product/edit/5 -> Edit(int id)
2       Query strings	    /search?q=book → Search(string q)
3       Form data	Form    POSTs (HTML forms)
4       Body (JSON)	      JSON payload in API
5       Headers	          Request.Headers["X-Token"]

-> Benefits of Model Bindings : 
1. Reuces boilerplate code
2. Clean and readable controller methods
3. Supports both smiple types and complex objects

-> Interview One-Liner:
"Model Binding ASP.NET Core ka feature hai jo rquest data ko automatically controller ke methods parameters ya model objects me convert karta hai - bina manual parsing ke".

## Q2 : How validation works in ASP.NET CORE MVC and how they follow DRY principle?
Ans : "Validation ka use hota hai user ke input ko check karne ke liya - ki vo sahi hai ya nahi , jaise empty na ho , email valid ho , etc."

-> Step By Step : How validation Works
1. You decorate your model with validation attributes
(using [Required],[StringLength],[EmialAddress],etc)
2. Model Binding fills the model with user input
3. ModelState.IsValid is checked in the controller to see if the data passed validation.
4. If not valid , the form is re-defined with error messages.

-> Example :
```c#
public class UserModel
{
    [Required(ErrorMessage = "Name is required")]
    public string Name { get; set; }

    [Range(18, 60, ErrorMessage = "Age must be between 18 and 60")]
    public int Age { get; set; }

    [EmailAddress(ErrorMessage = "Invalid email format")]
    public string Email { get; set; }
}
```
```C#
[HttpPost]
public IActionResult Register(UserModel user)
{
    if (ModelState.IsValid)
    {
        // Save to DB or proceed
        return RedirectToAction("Success");
    }

    // Show same form with validation errors
    return View(user);
}
```

->  How it follows the DRY(Don't Repeat Yourself) Principle : 
DRY Principle means : write once, use many times - dont duplicate logic.

In ASP.NET Core MVC :
1. You define validation once on the model using attributes
2. Same validation works for:
    1. Server-side (ModelState)
    2. Client-side (with unobtrusive JavaScript)
    3. Anywhere model is used (e.g., in different forms)
3.  So you don't write validation rules again in controller or view — it's all centralized!

# Razor View 
## Q1 : What is the MVC Pattern ?
Ans : MVC ek Software design pattern hai jisme application ko 3 parts me divide kiya jaata hai - Model(data) , View(UI) ,Controller(logic) - taaki code clean aur manageable rahe.

-> Components of MVC :
1. Model(M) 
- Represents data and bussiness logic 
- Interacts with the database
- Example : Product, User , ORder Class

```c#
public class Product {
    public int Id { get; set; }
    public string Name { get; set; }
}
```

2. View(V)
- Represents the UI (HTML + Razor)
- What the User Sees 
- Uses the data provided by the model

```html
@model Product
<h1>@Model.Name</h1>
```
3. Controller(C)
- Handles  User Requests
- Talks to Models and Send data to View
- Controls the Flow of the application

```c#
public class ProductController : Controller {
    public IActionResult Details(int id) {
        var product = GetProductById(id); // Model
        return View(product);             // View
    }
}
```

-> Real Life Analogy 
- Soho Ek Restaurant :
1. Customer (Browser) order karta hai
2. Waiter (Controller) order leta hai
3. Kitchen (Model) khana banata hai
4. Waiter customer ko khana deta hai (View)

-> Benifits Of MVC: 
Srno  Features                Benefits
1     Separation of Conserns  Code is organized and modular
2     Testability             Easy to write unit tests for Models and Controllers
3     Scalability             Easy to maintain and scale
4     Reusability             Views and logic are reusable

-> Interview One - Liner :
"MVC is a pattern that separates the application into Model(data), View(UI), and Controller(logic), making the code clean, testable and easier to manage - it's the foundation of ASP.NET Core Web Apps."

## Q2 : Explain the role of the various components of the MVC pattern?
Ans : Model : Repesents all the data and bussiness logic that the user works within a web application . In ASP.NET core , the model is repesented by C# classes that hold the data and related logic that operates on that data. The "Models" directory stores the model classes .
You can also write POCO (Plain - Old - CLR - Object) classes only for storing the data and write bussiness logic in a sapeate model class(a.k.a 'Services').

View : Represnets all the UI logic of the applicaiton . In a web applicaton , it represents the HTML that's sent to the user and displayed in the browser 
One important thing to remember is that all HTML code is not static or hard-coded. The HTML code in view can be generated dynamically using a model's data.

Controller: Acts as an interface between Model and View. It processes the business logic and incoming requests, manipulates data using the Model, and interacts with the Views to render the final output.
In ASP.NET, these are C# classes that form the glue between a model and a view. Controllers have action methods that act as middleware that execute upon receiving a HTTP request from the browser, then retrieve the data from model and pass it to the view to dynamically render a response. The controllers can be present in any folder – the common name of the folder is “Controllers”.

## Q3 : Explain the differences between ViewData and ViewBag?
Ans : ViewData aur ViewBag dono ka use Controller se View me temporary data bhejna ke liya hota hai,

-> Key Differences
Srno    Feature       ViewData              ViewBag
1       Type          Dictionary            Dynamic property
                      (ViewData["Key"])     (ViewBag.Name)

2       Syntax        ViewData["Name"]      ViewBag.Name = "Rahul";
                      = "Rahul";

3       Complie       No IntelliSence       IntelliSence supported
        Time check    error if wrong key    (Dynamic)  

4       Null Safety   Prone to nulls,       safer , no casting required 
                      must cast  

5       Introducted   ASP.NET(classic)      ASP.NET MVC 3
        In

6       Performace    Slightly Slower       Slighty Better Performance
                      (due to boxing
                      /unbxing)        

-> Example in Controller:

```c#
public IActionResult Index()
{
    ViewData["Message"] = "Hello from ViewData!";
    ViewBag.Note = "Hello from ViewBag!";
    return View();
}
```

```console
<h2>@ViewData["Message"]</h2>
<h2>@ViewBag.Note</h2>
```

-> Important Notes: 
- Both are short - lived , used only for current HTTP Request
- Neither is type-safe . For Complex data, prefer Model or ViewModel.

-> Real Life Analogy
"Socho Controller ek teacher hai jo View (student) ko ek chhoti si note deta hai:
ViewBag ek oral message hai (easy but informal),
ViewData ek written chitthi hai (structured but harder to parse)."

-> Interview One-Liner
"ViewData is a dictionary and ViewBag is a dynamic wrapper over it — both send data from Controller to View, but ViewBag is more readable and easier to use, while ViewData is older and more manual."

## Q4 : Explain Strongly Typed Views.
Ans : 
1. Strongly Typed view are tightly Bound to a model
2. The Strongly - Typed View can recelive model object (of Specific class)
3. The controller can supply model object by using the return View(model) method, at the end of action method.
4. You can use the strongly-typed tag helpers (such as asp-for) in strongly-typed views.

# Layout View
## Q1 : Explain the purpose and usage of layout views in asp.net core?
Ans : "Layout View ek template hai jisme website ke common parts jasie header. footer, navbar ko rakhte hai, --- taaki sab pages me repeat na karna pade."

-> Why Use a Layout View?
1. To follow the DRY(Don't Repeat Youself) Principle
2. Keep your Website's look consistent accross pages.
3. Make changes in one place (Layout)to reflect everywhere.

-> Structure of Layout Page
Usually stored in :
/Views/Shared/_Layout.cshtml

<!DOCTYPE html>
<html>
<head>
    <title>@ViewData["Title"] - MySite</title>
</head>
<body>
    <header>
        <h1>My Website Header</h1>
    </header>

    <nav>
        <!-- Menu here -->
    </nav>

    <main>
        @RenderBody()  <!-- Page-specific content will be injected here -->
    </main>

    <footer>
        <p>© 2025 MySite</p>
    </footer>
</body>
</html>

-> How to use Layout in a view
In Your Razor View(e.g. Index.cshtml)
@{
  Layout = "~/Views/Shared/_Layout.cshtml";
}

Or set the default layout in _ViewStart.cshtml:
@{
    Layout = "_Layout";
}

-> Real Life Analogy 
"Socho ek magazine ka cover page, header aur footer same rehta hai, par andar ke pages ka content alag hota hai —
Waise hi layout view ek common design frame hota hai, jisme har page ka content inject hota hai."

-> One Liner Interview :
"Layout view in ASP.NET Core is used to define the common structure (like header, footer, navbar) of the website — following the DRY principle by keeping shared content in one place and using @RenderBody() to insert page-specific content."

# Partial View
## Q1 : Explain partial views in asp.net core?
Ans :  A partial View in ASP.NET Core is like a reusabe component that contains a peice of HTML + Razor Code.

It is used to divide views it smaller parts or to reuse common UI blocks.
 
-> Use Case :
1. Reusable Components (like : Login forms, NAvigation bar , PRoduct card).
2. Breaking big views into smaller , manageable parts.
3. AJAX partial updated

## Q2 :  What is Difference between PartialAsync() and RenderPartialAsync() ?
Ans : 
1. PartialAsync() Return an IHtmlContent(string like result)  RenderPartialAsync() Writes directly to reponse (no return)
2. PartialAsync() Use when you wan to store/return HTML RenderPartialAsync() Use when yu wan tot write to page output
3. PartialAsync() Sligthly faster as it avoids buffereing RenderPartialAsync() slightly more flexible for output control.
