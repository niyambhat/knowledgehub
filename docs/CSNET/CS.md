---
sidebar_position: 2
---

## What is a Constructor? 
Three main features of a constructor:
* A special method responsible for initializing variable in that class.It is a non-value returning method.
* Each and every class requries a constructor if we want to create an instance.
* The name of constructor is same as the name of the method.


#### 1. Explicit & Implicit Constructors
* Each and every class requries a constructor if we want to create an instance.
* It is the responsibility of a programmer to add a constructor if not the Compiler itself adds one.
* If the varaibles are not defined. The Constructor assigns a default value as mentioned below. 

**Ex: Implicit constructor**
```csharp
class Test{
    int i;
    string s;
    boolean y;
}

Test obj = new Test(); //valid

```

Here the compiler turns implicitly as such,

```csharp
class Test{
    int i;
    {
        public Test(){
           i = 0; // done by compiler
           s = null;// done by compiler
           y = false;// done by compiler
        }
    }
    
}
Test obj = new Test()
```

**Ex: Explicit constructor**
```csharp
using System;

public class Person
{
    private string name;
    private int age;

    // Explicit constructor
    public Person(string name, int age)
    {
        this.name = name;
        this.age = age;
    }

    public void PrintDetails()
    {
        Console.WriteLine($"Name: {name}, Age: {age}");
    }
}
public class Program
{
    public static void Main()
    {
        // Creating an instance of Person using the explicit constructor
        Person person = new Person("John Doe", 30);
        person.PrintDetails();
    }
}

```
#### 2. Types of Constructors 

1. Default or Parameter less constructor
The compiler implicitly assigns a parameterless constructure if we dont define it.

```csharp
public class MyClass
{
    public MyClass()
    {
        // Constructor code here
    }
}
```
2. Parameterized Constructor
Explicitly defined by a constructor
```csharp
class ParameterizedConstructorDemo{
    public ParameterizedConstructorDemo(int i){
        Console.WriteLine("Demo"+i)
    }
}

```

3. Copy Constructor
Passing Same class as a parameter. 

4. Static Constructor
Static constructor are defined explicity
```Csharp
* Static constructors cannot be parameterized
* Static constructor run first.

class Test{
    static Test(){

    }
    public Test(){ //Implicitly defined

    }
}
```
### 3. 

