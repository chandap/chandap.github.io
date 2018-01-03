---
layout: post
title: Sorting a matrix 
---
Lets see how can we sort a $$ m \times n $$ matrix such that each row is sorted and each column is sorted in ascending order. It turns out that if you simply sort all the rows and then sort all the columns, the desired sorted state is achieved. But why is that ? 

Consider the following matrix : 

| a             | ...           | b     | ...  |  c  |
| :-----------: |:-------------:|:-----:|:----:|:---:|
| .             | .             | .     |  .   |  .  | 
| p             | .             |  q    | ...  |  r  |

