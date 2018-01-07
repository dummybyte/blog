---
layout: post
title: "Coding Best Practices"
description: "Introduction"
date: 2016-12-22
tags: [Best Practices]
comments: true
share: true
---
## Contents
- [Coding Best Practices](#CodingBestPractices)

## Coding Best Practices

The best practices mentioned here in the blog are references taken from "Clean Code" by Robert C. Martin.

- **Comments:** "Comments Lie". Use comments only if there is something your code couldn't explain. Remember the code you write will always be changed by someone in the near future. And people, while changing your code, will change your logic but will always forget to update the comments. So use them wisely.

- **Static/Non-Static Methods:** In general you should prefer non-static methods to static methods. When in doubt, always use non static methods. If you really want a method to be static make sure that there is no chance that you'll want it behave polymorphically.

- **Encapsulate Conditionals:** Extract functions that explain the intent of the conditional.
```
if (shouldBeDeleted(timer))
```
is preferred over
```
if (timer.hasExpired())
```
or any thing else.
Avoid negative conditionals. negative are a bit harder to understand than the positives.

- **Constants:** Never define a constant in an abstract class or an interface and use it in their particular implementations.

- **Miscellaneous:**
* One of the more powerful ways to make the program readable is to break the calculations up into intermediate values that
are held in variable with meaningful names.
* One-switch rule: There may be no more than one switch statement for a given type of selection. The cases in that switch statement must create polymorphic objects that take the place of other such switch statements in the rest of the system.
* Don't choose names that communicate implementation. Choose names that reflect the level of abstraction of the class or function you are working on.
