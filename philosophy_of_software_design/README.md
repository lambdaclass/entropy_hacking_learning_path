# Philosophy of Software Design

This document is a summary of the book Philosophy of Software Design.

## 1. It's All About Complexity

The greatest limitation in writing software is our ability to understand the systems we are creating. As a program evolves, complexity inevitably increases and the system becomes harder to understand, slowing down development and leading to bugs.
There are two general approaches to fighting complexity:
- Making code simpler and more obvious. For example, eliminating special cases or using identifiers in a consistent fashion.
- Encapsulate complexity, so that programmers can work on a system without being exposed to all of its complexity at once. This approach is called **modular design**, as the software system is divided up into modules designed to be relatively independent of each other.

## The Nature of Complexity

Recognize complexity allows you to identify problems before invest a lot of
effort in them, and it allows you to make good choices among alternatives.
_Complexity is anything related to the structure of a software system that
makes it hard to understand and modify the system_, if a software system is
hard to understand and modify, then it is complicated, otherwise is simple. In
terms of cost benefit. In a complex system, it takes a lot of work to implement
small improvements. In a simple one, larger improvements can be implemented
with less effort. Isolating complexity in a place where it will never be seen
is almost as good as eliminating the complexity entirely. Complexity is more
apparent to readers than writer if you write a piece of code and it seems
simple to you, but other people think it's complex, then it is complex. A
developers job is not just to create code that you can work easily, but to
create code that others can also work with easily.

Complexity manifests itself in three general ways:
- Change amplification: Simple change requires code modifications in many
  different places. One of the goals of good design is to reduce the amount of
  code that's affected by each design decision
