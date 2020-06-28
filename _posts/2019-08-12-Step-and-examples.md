---
layout: post
title: Step-by-Step Execution and Examples
tags: kde gsoc 2019
---

Last week I finished writing all the new examples for the ROCS, together
with a little description of each commented in the beginning of the code.
The following examples were implemented:

* Breadth First Search;
* Depth First Search;
* Topological Sorting Algorithm;
* Kruskal Algorithm;
* Prim Algorithm;
* Dijkstra Algorithm;
* Bellman-Ford Algorithm;
* Floyd-Warshall Algorithm;
* Hopcroft-Karp Bipartite Matching Algorithm.

It is good to note that while Prim algorithm and BFS were already in rocs,
they were broken and could not be run. The following image is an example 
of a simple description of an algorithm:

![Description]({{site.url}}/assets/desc.png "Description"){: .center-img}

About the step-by-step execution, I am considering our possibilities. My
first idea was to take a look into the debugger for the `QScriptEngine` 
class, which is the `QScriptEngineDebugger` class. An instance of this
class can be attached to our script engine, and it provides the programmer
with a interface with all the necessary tools.

Although useful, I personally think our rocs don't need all this tools.
(but they can be provided separately) There are 3 ways to stop the code
execution using this debugger:

* By an not treated Exception inside the javascript code;
* By a call to the **debugger** instruction, that automatically invokes the debugger interface;
* By a breakpoint, that can be put in any line of the javascript code.

The first one is not really useful for us, as it halts the code execution.
The second and the third can be really useful couple with an **Continue**
command. But the second invokes the full debugger interface, which we don't
really want.

![Debugger]({{site.url}}/assets/debugger.png "Debugger"){: .center-img}

So, by using the third one, we can stop the execution in any line of the
javascript code and create a step button with the **Continue** command to
continue executing the code. The only problem is how to add the breakpoints,
as there is no direct function to add them, and usually the programmer has
to use the `ConsoleWidget` interface or the `BreakpointsWidget` to do this.
The following image shows the **Continue** button, which is already working:

![Continue]({{site.url}}/assets/continue.png "Continue Button"){: .center-img}

But the challenge of adding the breakpoints still remains. One of my ideas
is to modify the code editor to accept an click on the line number bar, which
triggers an signal to add/remove an breakpoint to that line. This is an clean
alternative for me. But for that I have to check if the `KTextEditor` have
this type of signal and create a way to add breakpoints in the code by function.

---
