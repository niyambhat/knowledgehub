---
sidebar_position: 2
---

# Models

Keep it simple. 

MVC Concepts in C#.

## 1. How to create a simple website?

In ASP.NET, the controller has the methods to control the view. 
Process:
1. Create a Controller. 
   Ex: HomeController.

   Then inside, declare the functions with the same name as the pages you are about to create.

   ```csharp
   public class HomeController : Controller
   {
       //...
       public IActionResult Index()
       {
           return View();
       }
       
       public IActionResult About()
       {
           return View();
       }
       
       public IActionResult Programs()
       {
           return View();
       }
   }


2. Now, you can create a Razor page in the Views folder, inside the Home folder since it is in the HomeController. The functions About() or Programs() handle the request to the respective pages and are required for redirection. It looks for a view with the same name as the action method (About.cshtml in this case) within the appropriate view folder.

3. Check the view in the URL using:
/Home/About or /Home/Program

4. Use this method to create Multiple websites before you proceed:
Learn - Adding links to page in layouts, Building Pages, Controllers. etc. 
Accomplish atleast 3 Simple Projects to build a solid foundation.

## 1. How to customize the view Templete?
We can create dynamic sections and put into the pages in view. 
Ex: 
In this scenario, we create a Header.cshtml,
Then we call this in the About page. 


 

