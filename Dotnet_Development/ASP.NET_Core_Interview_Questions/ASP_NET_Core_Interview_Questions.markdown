# Basics ASP.NET Core Questions

## Q1 : What is ASP.Net Core ? (1)

Ans :-
-> Cross Platform, Open Source ,Free , High performace Framework For building cloud based applications , such as IOT apps, webapps and mobile backends .It is design to run on cloud as well as on - premises.

-> ASP.NET Core is not a upgraded version of ASP.NET

-> ASP.NET Core is completely rewriting that work with the .net Core framework. It is much faster , configurable, modular , scalable , extensible and has cross-platform support .

-> It is best suitable for coud based such as web apps, mobile apps, and IoT apps.

- SHORTCUT TO REMEMBER
  CROSS-FREE-HIGH-CLOUD
  CROSS → Cross-platform (Runs on Windows, Linux, macOS)
  FREE → Open Source & Free
  HIGH → High Performance (Fast, modular, scalable)
  CLOUD → Cloud-Based (Ideal for Web, Mobile, IoT apps)

  ASP.NET Core = Not just an upgrade, but a complete rewrite

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q2 : What are the features of ASP.NET Core ?(2)

Ans : Alright! Imagine you are building a toy house with LEGO blocks. ASP.NET Core is like a super cool LEGO sets that makes it easy to build your house (a web app).

1. Build - in supports for Dependency Injection
   Think of this like having a **magic toolbox** that always gives you right tool when you need it, **without you searching** for it.

2. Build-in Supports for logging framework
   Imagine you haveing a **notebook where you write down everything** that is happening while building your house - like when a brick falls or when you add a new door.

3. Kestrel web server (No need for IIS, Apache, Nginx)
   Normally, to show your toy house to other , you need a **big display table** (IIS, Apache,etc), but ASP.NET Core gives you a small , portable table (Kestrel) So you can show your house anywhere.

4. Supports multiple hosting platforms
   This means you can place your toy house on different types of tables—Windows, Linux, or Mac!

5. Modularity (Only take what you need)
   Instead of buying a gaint LEGO set, you can only pick the exact peices needed for your house . This makes you project light and fast/

6. Command Line Supoort
   think of it like talking to a robot using short words to tell it what to do : "build house" , "add roof" , "paint walls" This make working faster

7. No web.config file , uses appsettings.json
   Instead of keeping your house plans in a big, messy notebook, you use a neat, easy-to-read book called appsettings.json.

8. Asynchronous programming (Does multiple things at once)

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q3 : What are the advantages of ASP.NET Core over ASP.NET (.NET Framework)? (3)

Ans :

1. It offers faster performace due to its minimalistic design
2. It is cross platform , so it can be run on windows, Linux ,Mac.
3. It is Open source
4. There is no dependency on framework installation because all the required dependencies are shipped with our application to the production server.
5. Multiple deployment platforms available with ASP.NET Core.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q4 : What is ASP.NET Core meta package? (4)

Ans : Imagine you are getting a school backpack. Instead of adding books one by one , you get a ready- made "school essentials kit" that already has everything you need - books, pencils , and notebooks.

In ASP.NET Core .Microsift.AspNetCore.App is like that "school essentials kit". It include all the important tools(libraries) needed to build a web app, so you don't have to install each one separately.

**What is Shared Framework? **
-> Now Imagine you and your friends all do the same school, and the school provides common textbooks. You don't need to carry your own books every day because they are already available in the classroom.

-> Similarly, the ASP.NET Core Shared framework means that important files(.dll files) are already installed on your computer when you intall .NET Core 3.0 or later . So, you app doesn't need to bring its own copies - it just uses what’s already there!

<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net6.0</TargetFramework>
  </PropertyGroup>
</Project>

This Code Tells i'm in 6th grade, so give me 6th - grade books.
<Project Sdk="Microsoft.NET.Sdk.Web"> → This says, "I am a web project!"
<TargetFramework>net6.0</TargetFramework> → This says, "I want to use .NET 6!"
By using this setup, your project automatically gets all the necessary tools from Microsoft.AspNetCore.App without you adding them one by one.

In Short :

1. Saves Time : No need to install each library separatly.
2. Less Baggage – Your project stays light because it reuses common files.
3. Easy Updates – Microsoft maintains it, so you always get the latest fixes.

So, in short: Microsoft.AspNetCore.App is like a school essentials kit that includes everything you need to build a web app, and the shared framework makes sure you don’t carry extra weight!

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q5 : When do you choose Classic ASP.NET MVC over ASP.NET Core ? (5)

Ans : Through Asp.Net is better choice in almost every aspects, you don't have to switch to ASP.NET CORE if you are maintaning a legacy ASP.NET applications that you are happy with and that is no longer actively developed.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q6 : What is a Web application framework, and what are its benefits?(6)

Ans : Learning to build a application can be daunting. Most of the web applications have a standard set of functionality such as :

1. Build a dynamic response that corresponds to an HTTP request.

2. Allow users to log into the application and manage their data.

3. Store the data in the database.

4. Handle database connections and transactions.

5. Route URLs to appropriate methods.

6. Supporting sessions, cookies, and user authorization.

7. Format output (e.g. HTML, JSON, XML)

8. Improve security.
   Frameworks help developers to write, maintain and scale applications. They provide tools and libraries that simplify the above recurring tasks, eliminating a lot of unnecessary complexity.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

# Kestrel Secver , IIS Server, launchsettings.json

## Q1 : What is a Kestrel And What are advantages of Kestrel in ASP.NET Core ? (7)

Ans :
-> Kestrel is the default web server for ASP.NET Core Applications.
-> It is a lightweight , fast, and cross platform web server used to process HTTP requests in your application.
-> Think of it as a middleman between your application and the internet.
-> It listens for incoming web requests, processes them , and sends back responses.

Advantages :

1. Super Fast : Kestrel is optimized for speed and can handle many requests efficiently.
2. Cross-Platform : Works on Windows, Linux, and macOS, so you can run your applicaton anywhere.
3. Lightweigth : Uses fewer system resources, making it ideal for cloud-based applications.
4. Supports Latest Features : Works with modern web technologies like HTTP/2 , WebSockets, and gRPC for better performance.
5. Can work alone or with IIS/Nginx : You can use Kestrel as a standalone server or with a reverse proxy like IIS, Nginx, or Apache for extra security and load balancing.
6. Build In security : Supports HTTPS , request filtering , and other security features to keep your application safe.

How Does Kestrel Work :

1. A user makes a request (eg. opens your website.)
2. Kestrel recieves the request and processes it.
3. Your ASP.NET Core app handles the request and prepares a response.
4. Kestrel sends the response back to the user's browser.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q2 : What is the difference between IIS and Kestrel ?Why Do we need these two webservers (8)

Ans : The main difference between IIS and Kestrel is that Kestrel is a cross - platform server. It runs on Windows , Linux and Mac , where as IIS only runs on windows.

Another essential difference between the two is that kestrel is fully open - source ,where as IIS is closed source and developed and maintained only by microsoft.

IIS is very old software and comes with a considerable legacy and bloat. With kestrel, Microsoft started with high performace in mind. they developed it from scratch, which allowed them to ignore the legacy / compatibolity issues and focus on speed and efficiency.

However , Kestrel doesn't provides all the rich functionality of a fully fledged webserver such as IIS, Nginx .Hence , We typicallyuse it as an application server , with one of the above servers acting as a reverse proxy.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q3 : What is the purpose of launchsettings.json in asp.net ?(9)

Ans : launchsettings.json is a file in an ASP.NET Core project that stores settings for running your application during developement.

Think of it like a remote control that tells Visual Studio, dotnet run, or other tools how to start your app.

- Why is launchsettings.json important :

1. Defines How Your App Starts
   -> Tells which server to use (Kestrel ,IIS)
   -> Sets the enviroment (Developement, Production etc)
   -> defines the URL your app runs on (like https://localhost:5001).

2. Helps in Debugging
   -> It allows you to easily switch between different profiles when testing your app.

3. Speeds Up Development
   -> You don’t need to manually set configurations every time you run your app.

- Code "Properties/launchSettings.json"

```C#
{
  "profiles": {
    "IIS Express": {
      "commandName": "IISExpress",
      "launchBrowser": true,
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    },
    "MyApp": {
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

Breaking It Down in Simple Words:

1. "profiles" → Different ways to start your app (e.g., using IIS Express or Kestrel).
2. "commandName" → Defines the tool used to start the app.
3. "launchBrowser": true → Automatically opens a browser when the app starts.
4. "applicationUrl" → Defines the URLs your app runs on.
5. "ASPNETCORE_ENVIRONMENT" → Sets whether you’re in Development, Staging, or Production mode.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q4 : What is generic host or HostBuilder in .NET Core ?(10)

Ans : Imagine you are building a big toy house .You need :
-> Workers to build and maintain it.
-> Electricity and Water to run inside the house.
-> Rules to manage how things work inside.

In .Net , HostBuilder is like the manager who takes care of everything when building an applications(your "toy house").

- What does HostBuilder Do

1. Dependency Injection(Workers)
   -> It makes sure different parts of your app can work together without issues.
   -> Example: If your app needs a "database helper," HostBuilder provides it when required.

2. Service Lifetime Management (Who works when )
   -> Some workers need to work all the time, some only for a short time.
   -> HostBuilder manages when services start and stop.

3. Configuration (Electricity and Water)
   -> Your app needs settings (like URLs , database connections, or secret keys)
   -> HostBuilder reads these settings from files like appsettings.json or environment variables.

4. Logging (Rules and Reports)
   -> Keeps track of what's happening in the app.
   -> If something goes wrong, logs help developers understand the problem.

- Before & After in .NET
  -> Old Days (Web Host ) → Only worked for web apps.
  -> Now (Generic Host ) → Works for web, Windows, Linux, and console apps.

- In Short:
  -> HostBuilder is like a manager that organizes your app.
  -> It helps different parts of the app work together smoothly.
  -> It replaced the older Web Host to support all kinds of apps, not just websites.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q5 : What is the purpose of .csproj file ?(11)

Ans : Imagine You are Building a LEGO house. To build it , you need :

1. Instruction - What kind of house are you building
2. LEGO pieces - what parts do you need?
3. Rules - How to put everything together?

In .NET Project .csproj file is like the instrument manual that tells .NET :
-> What kind of project (game , website, app) you are building.
-> Which version of .NET it should use.
-> What extra tools(NuGet packages) it needs to work.

```XML
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net6.0</TargetFramework>  <!-- Using .NET 6 -->
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="PackageName" Version="1.0.0.0" />  <!-- Adding extra tools -->
  </ItemGroup>
</Project>
```

- Breaking it Down :

1. <Project Sdk="Microsoft.NET.Sdk.Web"> → We are making a web project
2. <TargetFramework>net6.0</TargetFramework> → We are using .NET 6
3. <PackageReference Include="PackageName" Version="1.0.0.0" /> → We are adding an extra tool to help our project (like getting a LEGO piece from a shop).

In Super Simple Terms :

1. .csproj is like a recipe for your project.
2. It tells .NET how to Build your app.
3. It includes extra tools(like LEGO pieces) to make he project work.
4. If something is missing, the app won't work properly..

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q6 : What Is IIS ?(12)

Ans : IIS stands for Internet Information Services. It is powerfull web server developed by microsoft. IIS can also act as a load balancer to distribute incomming HTTP requests to different servers to allow high reliablity and scalibility.

It can also act as a reverse proxy, i.e. accept a clients request, forward it to an application server, and return the clients response. A reverse proxy improves the security, reliability, and performance of your application.

A limitation of IIS is that it only runs on Windows. However, it is very configurable. You can configure it to suit your applications specific needs.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q7 : What is the “Startup” class in ASP.NET core prior to Asp.Net Core 6?(13)

Ans : Before .NET 6 ,every ASP.NET Core application needed a Startup class. This class was like the "starting point" of the app,where we set up everything needed for the app to work properly.

Think of Startup as the "Main Switchboard" of a building :
-> It wires up all services (like electricity , internet ,plumbing)
-> It sets up rules on how things should work.
-> It makes sures everything runs smoothly.

- What did the Startup Class contains?

1. ConfigureServices()(Setup the Toolbox)
   -> This method is used to register all the services your application needs.
   -> Services are like tools(e.g. database ,authentication, logging, etc.)
   -> It uses Depondency Injection(DI) to provide these tools when needed .

```c#
  public void ConfigureServices(IServiceCollection services)
  {
     services.AddControllers(); // Adds support for API controllers
     services.AddDbContext<MyDbContext>(); // Adds database connection
     services.AddAuthentication(); // Adds authentication system
  }
```

2.  Configure()(Setup the App Pipeline)
    -> This method defines how the app should handle requests.
    -> It adds Middleware, which are like security guards controlling traffic flow.
    -> Middleware decides who can enter, what is logged, and how responses are sent.

```c#
  public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
  {
   if (env.IsDevelopment())
   {
       app.UseDeveloperExceptionPage(); // Show detailed error pages in Development mode
   }

   app.UseRouting(); // Enable request routing
   app.UseAuthentication(); // Enable authentication
   app.UseAuthorization(); // Enable authorization

   app.UseEndpoints(endpoints =>
   {
       endpoints.MapControllers(); // Enable API controllers
   });
  }
```

- What Changed in .NET 6 and Later ?
  Before .NET 6 :
  -> We had a Startup.cs file to set up ConfigureServices() and Configure().
  -> We had a Program.cs file that started the app and called Startup.

  After .NET 6 :
  -> Startup.cs was removed – everything was moved to Program.cs instead.
  -> Now, we configure everything directly inside Program.cs.

- Why Did Microsoft Remove Startup.cs in .NET 6 ?
  -> Simplifies the Code -> Everything is now in Program.cs, reducing extra files.
  -> Less Boilerplate → No need to write two separate methods (Configure & ConfigureServices).
  -> Easier to Read & Maintain → The whole app setup is now in one place.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Q8 : What does WebApplication.CreateBuilder() do?(14)

Ans : Following
-> Configure the app to use Kestrel as Web server.
-> Specify to use the current project directry as root directory for application.
-> Setup the configuration sub-system to read setting from appsettings.json and appsettings.{env}.json to environment specific configuration.
-> Set Local user secrets storage only for the development environment.
-> Configure environment variable to allow for server-specific settings.
-> Configure command line arguments (if any).
-> Configure logging to read from the Logging section of the appsettings.json file and log to the Console and Debug window.
-> Configure integration with IIS
-> Configure the default service provider.

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

# das
