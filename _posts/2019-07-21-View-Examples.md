---
layout: post
title: View and Examples
tags: kde gsoc
---

This week I began learning about QML to try to fix the View that show the graphs
and tools for manipulating graphs. More precisely, I wanted to deal with some problems:

* Vertexes that go near the border of the view cannot be moved;
* `Ctrl-A` do not select all the view, just a limited part;
* The option menu in the `Create Node` and `Create Edge` puts the lateral menu over the scroll bar;
* The scroll bar in the view don't have much use, as the view is tiny, and the mouse can be used to move in most cases;
* The `Flickable` motion from the Qt is stealing most of the clicks from the MouseArea (maybe remove the `interactive` option while outside the `Select/Move`?), making really difficult to create new edges;
* The Icons for the tools are not being showed.

This is the view now:

![Old View]({{site.url}}/assets/old_view.png "Old View"){: .center-img}

This is an probable new view (under implementation), that I will present
to my mentors:

![New View]({{site.url}}/assets/new_view.png "New View"){: .center-img}

I have been studying **QML** to modify this view and little by little I am building it.
Moreover, I modified the two original examples in the code `BreadthFirstSearch` and
`PrimSpanningTree` to work in the current system (they were with commands not valid
for the current version, like `interrupt()`). I also added one more example for the
other search algorithm, `DepthFirstSearch` and the other implementations are under
way:

* Topological Sorting Algorithm;
* Kruskal Algorithm;
* Dijkstra Algorithm;
* Bellman-Ford Algorithm;
* Floyd-Warshall Algorithm;
* Bipartite Matching Algorithm.

I had some other ideas for the interface that can be easily implemented and is a good
way to improve the workflow:

![Interface]({{site.url}}/assets/interface.png "Interface"){: .center-img}

This configuration create more space for the programmer while leaving enough space
to visualize the graphs correctly and it works well with a new horizontal toolbar. 

---

The new view is not yet available, as it is only local code. The new algorithm for DAG
creation and examples are available in the merge requests [here](https://invent.kde.org/kde/rocs/merge_requests/3https://invent.kde.org/kde/rocs/merge_requests/3) and [here](https://invent.kde.org/kde/rocs/merge_requests/4), respectively.

(Also, I have been really sick in the last week, but now I think I am better!)

---
