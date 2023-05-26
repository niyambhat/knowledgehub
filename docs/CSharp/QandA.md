---
sidebar_position: 4
---

# C# Workout: 10-Minute Session (Session A) 

## Table of Contents
----

  1. [Explicit vs Implicit Constructor](#constructor)
  1. [Variables](#Variables)
  1. [Access Specifiers](#access)
 

#### Explicit vs Implicit Constructor {#constructor}
**1. Does a class get a constructor if not defined by the programmer?**
    
    Yes

**2. Why do we need explicit constructor if the implicit constructor gets auto defined by Compiler**

Implicitly constructors a required in initialise the variables of a class with the same valueeven if we create multiple instances of the class. If we define constructors explicityl with paramenters then we get a chance of initializing the fields of the class with a new value every time we are going to createa instance of that class. 

Note: Generally every class requrie some values for execution and the values that is requored fora class are sent by constructor.

#### Variables {#Variables}
**3. What is a class?**

A class is a user-defined type.
> Did you know that "string" is also a type.
```
string = "Hello"; //no memory allocation
but,
string name = "Hello"; //creates an instance of string with new value
```

**4. Differences between variable, instance and reference of a class?**

- Variable
- Instance
- Refefrence 

```csharp
namespace First{
int x = 100; // varaiable of class 
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
            First f = new First(); // f is instance of the class
            Console.WriteLine(f.x); //
        }
    }
}



```
#### Access Specifiers {#access}

**5. What is Access Specifier?**

Five types of access specifier:
- Public: Straight-forward, accesible from everywhere
- Private: Is only accesible only within the class it was defined
- internal 
- protected: Within class and child classes
- protected internal

```csharp
using System;
namespace Project
{
	public class Person
	{
        public void Test0()
        {
            Console.WriteLine("public method");
        }
        private void Test1()
        {
            Console.WriteLine("private method");
        }
        internal void Test2()
        {
            Console.WriteLine("internal method");
        }
        protected void Test3()
        {
            Console.WriteLine("protected method");
        }
        protected internal void Test4()
        {
            Console.WriteLine("protected internal method");
        }
    }
}

```

Case One: Consuming members of a class from the same class

Case Two: Consuming members of a class from a child class on same project

Case Three: Consuming members of a class from non child class

Case Three: Consuming members of a class from non child class on different project

**6. Different kinds of variable of a class?**
Varaible stores a value. Four different kinds of varaibles in a class:
Non-Static(Instance variable), Static(Maintains one value for the whole class), Constants, ReadOnly(Creates upon initialisation)

- Non-Static
- Static: Explicitly declare by using "static" modifier, or under any static block.
Static variable doesnot require the instance of the class to be created for it to be used
```
{
    int x;
    static int x;
}
```
- Constant : Declared using a keyword const. These values cannot be redeclared. 
- Read only

> Understanding Basic Memory Management in C# 

**7. Explain what happens in the memory when an instance of the given clas is created?**

```
public class User{
int x =100;
static int y =200;
const float pi = 3.14f;
    public User{
        pass
    }
    static void Main(){
        User one = new User();
        User two = new User();
    }
}
```

Ans:
```
public class User{
int x =100;
static int y =200;
readonly int q = 1;
const float pi = 3.14f;
    public User{
        pass
    }
    static void Main(){
        // When the instance gets created. Each instance have its own separate memory and stores x
        // y & pi is only created once
        // q is read only but is created on each instance.
        User one = new User(); 
        User two = new User(); 
    }
}
```

**7. Explain what happens in the memory when an instance of the given clas is created?**

```
public class User{
int x =1;
readonly int q = 1;
static int x =2;
const x = 2;
    public User{

    }
      static void Main(){
        User one = new User();
        User two = new User();
    }
}
```

**7. get Set?**


## See also

* https://link-to-more-info