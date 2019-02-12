---
title: Automatic Transit Route Generation
author: Alexander Fleischer 
date: \today
...

# Introduction
A transit system consists of a set of $N$ lines $[L_1, \dots, L_N]$. These lines
are owned by $M$ operators $[Op_1, \dots, Op_M]$. Naturally,
$$M\leq N$$
In the following, I propose a method to automatically generate a set of routes
for each of the operators so that every stop in the system.
A relevant use-case for this is to minimize the amount of time spent on hanging
up timetable posters.

# Outline of Method
A path $P$ consists of $n_p$ stops. For each path, there are one or more
(transit) lines, $L_i$, that operates it.
$P$ can either be a *single-line path (SLP)* or a *multi-line path (MLP)*. 
An SLP is the path of a line that shares none of its stops with other lines.
On the other hand, an MLP is a path that two or more lines share.

An arbitrary MLP can be visualized as
$$
  MLP_1
    \begin{cases}
      Op_1\begin{cases}L_1\\L_2\end{cases}\\
      Op_3\begin{cases}L_8\end{cases}\\
      Op_6\begin{cases}L_3\\L_9\\L_{11}\end{cases}
    \end{cases}
$$
