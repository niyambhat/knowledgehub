---
sidebar_position: 3
---

1. Does a class get a constructor if not defined by the programmer?
True

2. Why do we need explicit constructor if the implicit constructor gets auto defined by Compiler?
Implicitly constructors a required in initialise the variables of a class with the same valueeven if we create multiple instances of the class. If we define constructors explicityl with paramenters then we get a chance of initializing the fields of the class with a new value every time we are going to createa instance of that class. 

Note: Generally every class requrie some values for execution and the values that is requored fora class are sent by constructor.

3. Differences between variable, instance and reference of a class?
A class is a user-defined type.
Did you know that "string" is also a type.
Ex: 
string = "Hello"; //nothig uses memory
but,
string name = "Hello"; //creates a copy of string with new value

a. Variable:
b. Instance
c. Refefrence 

```csharp


namespace First{
int x = 100;
    class First{
        static void Main(string[] args)
        {
            Console.WriteLine(x); //errors because x is an instance member
        }
    }
    
// This works as f now gets a memory
     class First{
        int x = 100;
        static void Main(string[] args)
        {   
            First f = new First();
            Console.WriteLine(f.x); //
        }
    }
}



```