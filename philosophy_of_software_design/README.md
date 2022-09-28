# Philosophy of Software Design

This document is a summary of the book Philosophy of Software Design.

## 1. It's All About Complexity

The greatest limitation in writing software is our ability to understand the systems we are creating. As a program evolves, complexity inevitably increases and the system becomes harder to understand, slowing down development and leading to bugs.
There are two general approaches to fighting complexity:
- Making code simpler and more obvious. For example, eliminating special cases or using identifiers in a consistent fashion.
- Encapsulate complexity, so that programmers can work on a system without being exposed to all of its complexity at once. This approach is called **modular design**, as the software system is divided up into modules designed to be relatively independent of each other.

## 3. Working code isn't enough
Be a strategical programmer instead of a tactical programmer. 

This is what being each other means:
- **Strategical programmers**: they won't accept to introduce unnecessary complexities to finish their tasks faster. The most important thing to them is the long-term structure of the system. They'll take a little extra time to find simpler designs for every implementation and to solve any design problem they find (they have an investment mindset).
- **Tactical programmers**: their main focus is to get something working without spending too much time thinking about the design.

If you implement a tactical programming approach, instead of continually making small improvements to the system design (strategical programming) you will be adding complexity. You should have an investment mindset.
