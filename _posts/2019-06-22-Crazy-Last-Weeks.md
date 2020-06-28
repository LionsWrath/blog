---
layout: post
title: Crazy Last Weeks
tags: kde gsoc 2019
---

Last weeks have been crazy for me. Since the GSoC began, I have been rushing everything related
to university and my life to dedicate exclusively to the development. Besides the two classes I
was taking, [Static Code Analysis](https://homepages.dcc.ufmg.br/~fernando/classes/dcc888/) and
Approximation Algorithms, I had my obligatory teaching internship in Project and Analysis of
Algorithms for the postgraduate program, where I was responsible for creating and evaluating
assignments for 50+ students and answering general questions.

![LAGOS](http://www.lagos2019.dcc.ufmg.br/wp-content/uploads/2019/05/logo-lagos-9.png)

Besides that, I was in the organization of the [Latin & American Algorithms, Graphs and 
Optimization Symposium](http://www.lagos2019.dcc.ufmg.br/) during June 2nd to 7th, where I was
responsible for a plethora of things before and during the event (Although it was a lot of fun, 
a lot of researchers from all around the globe and incredible research). And, just as I got back, 
I had to delve back to tests, assignments, seminars...

One of the problems for brazilians in taking the GSoC is that the beginning of the program does not
match exactly with the end of our classes. But now, as everything is (finally!) ending, I can focus
entirely in the GSoC and my project. Just before the GSoC (and before even creating my project), I
had compiled to KDE Framework 5 and the ROCS software, so most of the development environment
was already set.

I am using as my environment the Qt Creator, and I am focusing in the algorithm for creation
of specific graph classes inside the *generategraphwidget*. I have already implemented algorithms
for Paths, Complete and Complete Bipartite graphs, besides fixing some details here and there.
These modifications are still only in my local machine, as I am having some problems pushing the
commits (I must be doing something wrong in my configuration).

I noticed that the calculation of the position of the graphs generated is strange, as it put the
graphs almost ouside the view (and we can't push the view there), so probably the positioning
must be corrected. There is a function for calculating the center there, I will compare that
function to the point where the view always come back and adjust accordingly. Another detail
is the symbols of the view tools, that are not showing correctly.

-----
