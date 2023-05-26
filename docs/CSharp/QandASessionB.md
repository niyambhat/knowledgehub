---
sidebar_position: 4
---

# C# Workout: 10-Minute Session (Session B) 

## Table of Contents
----

1. [Explain the five pillars of Object-Oriented Programming (OOP)?](#oop)
1. [How is Inheritance implemented in C#?](#inheritance)
1. [What is the Parent class of all the classes?](#object)
1. [What are different types of Inheritance?](#typesofinheritance)
1. [What are different types of Inheritance?](#object)



----

#### 1. Explain the five pillars of Object-Oriented Programming (OOP)? {#oop}
Let us take a reference from human brain to learn the basic mechanism, 
1. **Encapsulation:** The neurons and synapses within the brain are encapsulated, allowing them to function independently and protect the delicate neural connections.

2. **Inheritance:** Genetic traits related to brain structure, such as certain cognitive abilities, can be inherited from parents to their children.

3. **Polymorphism:** The brain can process different types of information, such as visual, auditory, and tactile, using the same cognitive processes but adapting to different stimuli.

4. **Abstraction:** The brain abstracts complex concepts and experiences, allowing us to think in higher-level concepts rather than dealing with every minute detail.

5. **Association:** The brain forms associations between different ideas and memories, allowing us to make connections and recall information when needed.


---
#### 2. How is Inheritance implemented in OOP?{#inheritance}
Tags: DRY 

Inhertiance is a mechanism of comsuming members of one class in another by establishing parent-child relationship. By doing so all the members of Child class has access to the parent class. *** Reusability ***

Parent => Parent, Base or Super
Child  => Derived

Child class can consume the member of Parent class as if it is the owner of the class, 
except *** private *** members of the parents.

```csharp
using System;
namespace IntroCS
{
	public class Parent
	{
        public Parent() {
            Console.WriteLine("Parent Constructor");
        }
		public void Test1() {
			Console.WriteLine("Method 1");
		}
        private void Test2()
        {
			Console.WriteLine("Method 2");
        }
    }
}

namespace IntroCS
{
    public class Child : Parent
    {
        public Child() {
            Console.WriteLine("Child Constructor");
        }
        public void Test3() {
            Console.WriteLine("Method 3");
        }
        static void Main() {
            Child one = new Child();
            one.Test1();
            Console.WriteLine(one.)
            //one.Test2(); //no access
            one.Test3();
        }
    }
}

```
> *** Note: Sequence of calling the function: One calls Parent.Test1(). Child can treat the menmers of their parents but the method still does belong to parents.***

Constructors:
* Both classes get implicit constructor at this example. 
* Parent class constructor must be accesible to child class otherwise inheritance is not possible

---
#### 3. What is the Parent class of all the classes?**{#object}


Every class this is defined by us  or pre-defined in the library has a default parent clas .i.e *** Object *** class which is of System namespace. 
(Equals, GetHashCode, GetType, ToString) are the methods which all the other classes inherit from the object class and is accesible from anywhere.

---
#### 4. What are different types of Inheritance?**{#typesofinheritance}

On the basis of:
- **Number of parents a child can have:** 
- **Number of child a parent can have:** 

Types:
1. Single 
2. Multi-Level
3. Hierarchical
4. Multiple 
5. Hybrid

![Alt Text](../../src/Assets/Inheritance.png)


## See also

* https://link-to-more-info
