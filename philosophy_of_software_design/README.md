# Philosophy of Software Design

This document is a summary of the book Philosophy of Software Design.

## Chapter 1
### Introduction
### (It's All About Complexity)

Programming requires a creative mind and the ability to organize your thoughts. If you can visualize a system, you can probably implement it in a computer program. As a program evolves, complexity inevitably increases and the system becomes harder to understand, slowing down development and leading to bugs.
Good development tools may help, but building more powerful systems more cheaply will come from simpler designs.
There are two general approaches to fighting complexity:
- Making code simpler and more obvious. For example, eliminating special cases or using identifiers in a consistent fashion.
- Encapsulate complexity, so that programmers can work on a system without being exposed to all of its complexity at once. This approach is called modular design, as the software system is divided up into modules designed to be relatively independent of each other.
In the early days of programming design was often concentrated at the beginning of the project, such as in the waterfall model, where each phase completes before the next phase starts and different people are responsible for each phase. The entire system is designed in the design phase and subsequently implemented. Modern approaches tend to understand software design as a continuous process that spans the entire lifecycle of a software system, based on the knowledge that it's not possible to visualize the design for a large software system and its complexity before building anything, and using an incremental approach such as agile development. This implies that design happens continuously over the life of a system: developers should always be thinking about design issues, and the initial design for a system or component is rarely the best one; experience inevitably shows better ways to do things.
