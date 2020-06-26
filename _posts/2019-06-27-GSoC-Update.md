---
layout: post
title: GSoC Update
tags: kde gsoc
---

Last post I said that I was having some problems pushing my modifications to the
git repo. I discovered that the official ROCS repository was recently moved to
the KDE Gitlab repo, called [KDE Invent](https://invent.kde.org/), where I am
working on a fork of the [original ROCS repo](https://invent.kde.org/kde/rocs).

It is a model that I have some knowledge, as I already worked with gitlab in a
past internship and did some merge requests because of the [Hacktoberfest](https
://hacktoberfest.digitalocean.com/) (I like to win t-shirts). So I had to update 
my remote of the local repo and I sent my update to my remote fork branch, called
`improved-graph-ide-classes`.

When I was modifying the code, I noticed some problems with the creation of random 
trees, but I am thinking what is the better way to fix this part. This problem
lies in the relation of the algorithm and the edge types available to generate the
tree. When using directed edges, the code is sometimes generating directed loops
of size 2 in the graph.

![Directed Loops]({{site.url}}/assets/loops.png "DAG Loop"){: .center-img }

Theorically speaking, the definition of a tree must have undirected edges, otherwise
it would be a Directed Acyclical Graph (DAG). There are different algoritms to
generate them with different uses. For example, to generate random trees for a 
given number of nodes, you could choose an algoritm that can generate any tree
of the given number of nodes with the same chance \[[paper](https://link.springer.
com/chapter/10.1007%2F3-540-44862-4_95)\] (that means, the algoritm
has a uniform distribution of trees when a good seed is guaranteed). As for DAG's,
we can use an ranking algorithm to configure the height and width of the graph,
which could be more useful in most cases. While there can exist a algorithm to
generate both, I think it would be more useful to separate them.

But then enter the problem: It is not guaranteed that a undirected/directed
edge type will exist within the Edge Types of the program, as the user has the
freedom to add and modify any edge type. I found two ways to solve it:

* Always have an undirected and a directed edge in the edge types;
* Put a check on the interface to check whether the edge is directed or undirected when necessary;

This decision boils down to restrict or not the freedom of the user. Although
this not change much on the greater scope of the program, we have to decide
if the best way to go is to always force the user to check for the existence
of a necessary edge type, or just set two edge types that will always exist 
and work by restricting the modification of the edges.

-----

Next post I will talk about the identifier part of the ROCS system, as it
is a part of ROCS that needs some more polish.

-----
