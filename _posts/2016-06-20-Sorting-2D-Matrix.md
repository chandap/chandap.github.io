---
layout: post
title: Sorting a matrix 
---
Lets see how can we sort a $$ m \times n $$ matrix such that each row and each column is sorted in ascending order. It turns out that if you simply sort all the rows and then sort all the columns, the desired sorted state is achieved. But why is that ? 

Consider the following matrix : 

![an image alt text]({{ site.baseurl }}/images/matrix.png "2D matrix with m rows and n columns"){:height="50%" width="50%"}

Assume that all the $$m$$ rows are already sorted in ascending order. So $$a \leq b \leq c$$ and $$p \leq q \leq r$$. 

Now if we sort column 1, assume that the positions of $$a$$ and $$p$$ are swapped. Can this disrupt the sorted order in row 1, i.e, can this make $$p > b$$ ?

If the positions of $$a$$ and $$p$$ are swapped, we have $$ a \geq p $$, which implies $$ b \geq p $$ (as $$b \geq a \geq p$$). So the order in row 1 is not disrupted. 

Again, assume that columns 1 to $$k - 1$$ are already sorted in addition to the rows. Assume it did not disrupt the order of the elements in row 1. Now lets sort column $$k$$. Now let $$ q < b $$ so that they are swapped during sorting column $$k$$. 

Can this now disrupt row 1, i.e. can $$ q < a $$ ? As we have $$ p \leq q \leq r$$ and $$a \leq p$$, so $$a \leq q$$. 

Again, can $$ q > c $$ ? Well, $$ a \leq b \leq c$$ and $$q < b$$. So $$q < c$$. 

# How can we sort all the matrix elements efficiently ?

Remember, the rows and columns are already sorted. So an efficient way to merge min($$m$$,$$n$$) sorted arrays is needed.



