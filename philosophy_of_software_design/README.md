# Philosophy of Software Design

This document is a summary of the book Philosophy of Software Design.

## 1. It's All About Complexity

The greatest limitation in writing software is our ability to understand the systems we are creating. As a program evolves, complexity inevitably increases and the system becomes harder to understand, slowing down development and leading to bugs.
There are two general approaches to fighting complexity:
- Making code simpler and more obvious. For example, eliminating special cases or using identifiers in a consistent fashion.
- Encapsulate complexity, so that programmers can work on a system without being exposed to all of its complexity at once. This approach is called **modular design**, as the software system is divided up into modules designed to be relatively independent of each other.

## 2. The Nature of Complexity

_Complexity is anything related to the structure of a software system that
makes it hard to understand and modify the system_, if a software system is
hard to understand and modify, then it is complicated, otherwise is simple. In
a complex system, it takes a lot of work to implement small improvements. In a
simple one, larger improvements can be implemented with less effort. Isolating
complexity in a place where it will never be seen is almost as good as
eliminating the complexity entirely. If you write a piece of code and it seems
simple to you, but other people think it's complex, then it is complex. A
developers job is not just to create code that you can work easily, but to
create code that others can also work with easily.

Complexity manifests itself in three general ways:
- Change amplification: Simple change requires code modifications in many
  different places.
- Cognitive Load: A high cognitive load means that the developer needs to spend
  a lot of time learning the required information and there is a greater risk
  of bugs because they missed something important. **Sometimes an approach that
  requires more lines of code is actually simpler, because it reduces cognitive
  load**
- Unknown Unknowns: It's not clear which pieces of code must be modified to
  complete a task or what information a developer must have to carry out the
  task successfully. This is the worst symptom of complexity.

Complexity is caused by two things: _dependencies_ and _obscurity_. A
dependency exists when a piece of code cannot be understood and modified
without understand another piece of code. The idea is to reduce dependency and
make it as simple and obvious as possible. Obscurity occurs when information is
not obvious. Obscurity is often associated with dependency and inconsistency.
The need for extensive documentation is often a sign that the design isn't
quite right. Complexity is incremental, it comes from an accumulation of
dependencies and obscurities.

## 3. Working code isn't enough
Be a strategical programmer instead of a tactical programmer. 

This is what being each other means:
- **Strategical programmers**: they won't accept to introduce unnecessary complexities to finish their tasks faster. The most important thing to them is the long-term structure of the system. They'll take a little extra time to find simpler designs for every implementation and to solve any design problem they find (they have an investment mindset).
- **Tactical programmers**: their main focus is to get something working without spending too much time thinking about the design.

If you implement a tactical programming approach, instead of continually making small improvements to the system design (strategical programming) you will be adding complexity. You should have an investment mindset.

## 4. Modules Should be Deep

Modular design attempts to minimize the dependencies between the modules that conform a system, trying to keep them as independent as possible from each other.

We think of each module in two parts:
  - Interface: it abstracts the module, describing _what_ it does.
  - Implementation: the code that carries out what the interface states.

An abstraction is a simplified view of an entity, which omits unimportant details. In modular programming, each module provides an abstraction in the form of its interface. Separating the interface of a module from its implementation helps to hide the complexity of the implementation from the rest of the system.

We could also classify modules into two categories:
  - Deep modules: they provide powerful functionalities hidden behind simple interfaces. It's a good abstraction because only a small fraction of its internal complexity is visible to its users.
  - Shallow modules: a relatively complex interface in comparison to the functionality that it provides. They give a small benefit in comparison to the cost of learning and using their interfaces.

![Deep vs shallow diagram](figures/deep_vs_shallow.png)

## 5. Information Hiding (and Leakage)

The most important technique for achieving deep modules is _information hiding_. Each module should encapsulate a few pieces of knowledge, which represents design decisions. The hidden information consists of details about how to implement some mechanism. This technique reduces complexity in to ways:
- The interfaces reflects a simpler and more abstract view of the module's capability so it reduces the cognitive-load for other developers.
- It makes easier to evolve the system since the hidden information it's not being used outside the module.

The best form of information hiding is when information is totally hidden within a module so is invisible to users of the module. Declaring methods or variables as _private_ can help but getters and setters make the information as public as if the variables were public.

The opposite of information hiding is _information leakage_. This occurs when the same knowledge is used in multiple places creating a dependency between modules. There's two common natures of information leakage, leaking through the interface or back-door leakage when two modules depends on the same piece of knowledge so if a change is needed both modules will need to be modified.

Information hiding can often be improved by making a module slightly larger. All the code for one capability should be in one single module to produce simpler interfaces (this relates to the module depth idea from previous section). Default values illustrate an example of partial information hiding, whenever possible a module should "do the right thing" without explicitly have to declaring to it. Information hiding also applies within a module encapsulating information between methods and minimizing the places where variables needs to be accessed by other methods. 

It's important to not hide information if the information is needed outside its module or if it affects directly the module behaviour.

## 7. Different Layer, Different Abstraction

In a well-designed system, each layer provides a different abstraction from the layers above and below it. Adjacent layers with similar abstractions, such as pass-through methods as a result of a bad division of responsibilities, are a red flag.                     
         
The solution is to refactor the classes, typically following one of the following approaches:
 - Expose the lower level class directly to the callers of the higher level class, removing all responsibility for the feature from the higher level class.
 - Redistribute the functionality between the classes.
 - If the classes can't be disentangled, merge them.

There are some exceptions where interface duplication is accepted, as in dispatcher methods, where the method uses its arguments to select one of several other methods to invoke, which often have the same signature as the dispatcher. Here the dispatcher provides useful functionality, choosing which of several other methods should carry out each task. 

