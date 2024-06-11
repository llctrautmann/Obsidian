---
title: notes on murphy
date:
  - 10-06-2024
time: 17:19
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-11
---
# notes on murphy

> [!PDF|yellow] [[murphy2022.pdf#page=258&selection=70,0,70,74&color=yellow|murphy2022, p.228]]
> > We can view a matrix as a set of columns stacked along the horizontal axis

> [!PDF|yellow] [[murphy2022.pdf#page=258&selection=136,0,136,75&color=yellow|murphy2022, p.228]]
> > We can also view a matrix as a set of rows stacked along the vertical axis:

> [!PDF|yellow] [[murphy2022.pdf#page=258&selection=306,0,326,1&color=yellow|murphy2022, p.228]]
> > If a square matrix satisfies A = AT, it is called symmetric. We denote the set of all symmetric matrices of size n as Sn.

> [!PDF|yellow] [[murphy2022.pdf#page=258&selection=332,0,337,10&color=yellow|murphy2022, p.228]]
> > A tensor (in machine learning terminology) is just a generalization of a 2d array to more than 2 dimensions

> [!PDF|yellow] [[murphy2022.pdf#page=259&selection=35,0,43,13&color=yellow|murphy2022, p.229]]
> > The number of dimensions is known as the order or rank of the tensor

> [!PDF|yellow] [[murphy2022.pdf#page=259&selection=82,11,91,55&color=yellow|murphy2022, p.229]]
> >  we can reshape a vector into a matrix. There are two choices for how to do this, known as row-major order (used by languages such as Python and C++) and column-major order (used by languages such as Julia, Matlab, R and Fortran

> [!PDF|yellow] [[murphy2022.pdf#page=260&selection=107,30,116,41&color=yellow|murphy2022, p.230]]
> > A vector space is a collection of such vectors, which can be added together, and scaled by scalars (1-dimensional numbers), in order to create new points. 

> [!PDF|yellow] [[murphy2022.pdf#page=260&selection=167,0,187,48&color=yellow|murphy2022, p.230]]
> > A set of vectors {x1, x2, . . . xn} is said to be (linearly) independent if no vector can be represented as a linear combination of the remaining vectors

> [!PDF|yellow] [[murphy2022.pdf#page=260&selection=257,0,287,1&color=yellow|murphy2022, p.230]]
> > The span of a set of vectors {x1, x2, . . . , xn} is the set of all vectors that can be expressed as a linear combination of {x1, . . . , xn}.

> [!PDF|yellow] [[murphy2022.pdf#page=261&selection=73,0,89,47&color=yellow|murphy2022, p.231]]
> > A basis B is a set of linearly independent vectors that spans the whole space, meaning that span (B) = Rn. There are often multiple bases to choose from

> [!PDF|yellow] [[murphy2022.pdf#page=261&selection=136,0,200,0&color=yellow|murphy2022, p.231]]
> > A linear map or linear transformation is any function f : V → W such that f (v + w) = f (v) + f (w) and f (a v) = a f (v) for all v, w ∈ V

> [!PDF|yellow] [[murphy2022.pdf#page=261&selection=200,2,217,58&color=yellow|murphy2022, p.231]]
> > Once the basis of V is chosen, a linear map f : V → W is completely determined by specifying the images of the basis vectors, because any element of V can be expressed uniquely as a linear combination of them.

> [!PDF|yellow] [[murphy2022.pdf#page=261&selection=387,2,398,1&color=yellow|murphy2022, p.231]]
> > The range (sometimes also called the column space) of this matrix is the span of the columns of A.

> [!PDF|yellow] [[murphy2022.pdf#page=261&selection=434,0,436,1&color=yellow|murphy2022, p.231]]
> > The range can be thought of as the set of vectors that can be “reached” or “generated” by A
> 
> 

> [!PDF|yellow] [[murphy2022.pdf#page=261&selection=447,23,466,0&color=yellow|murphy2022, p.231]]
> > The nullspace of a matrix A ∈ Rm×n is the set of all vectors that get mapped to the null vector when multiplied by A

> [!PDF|yellow] [[murphy2022.pdf#page=262&selection=140,0,147,1&color=yellow|murphy2022, p.232]]
> > The span of the rows of A is the complement to the nullspace of A.




