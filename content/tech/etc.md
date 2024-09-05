+++
title = 'Etc'
date = 2024-08-17T04:33:12+08:00
draft = true
+++

```
$ apt-cache search <name>

$ sudo snap install cmake --classic
```

csc\_matrix: Compressed Sparse Column matrix

```
form scipy.sparse import csc_matrix

csc_matrix((data, indices, indptr) , [shape=(M,N)])

```
is the standard CSC representation.
where the row indices for column **i** are stored in 
**indices[indptr[i]:indptr[i+1]]** and their corresponding values are store in 
   **data[indptr[i]:indptr[i+1]]**. 

- flatten circuit hierarchy then simulation
- map node name with subcircuit to integer 
- build node voltage? matrix
- klu solve
	- Ai, Ap, Ax, B
- update time

- calculate iv-curve
```
ivcurve(xpar, xmin, xmax, dx, xback, yexpr, yeps, twait, tmin, tmax)

calculate iv-curve
--------------------------
xpar - parameter to change. Can be found by function find(). For example find('.i1', 'p')
xmin - minimal value of parameter
xmax - maximal value of parameter
dx - step for parameter's changes
xback - if False parameter will be changed from xmin to xmax.
        if True parameter will be changed from xmin to xmax and when back to xmin
yexpr - expression to average over the time for each value of parameter xpar
        Can be calculated by function create_expression(). For example create_expression("v(j1)", ".")
yeps - relative accuracy to average expression yexpr over time
twait - wait time between changing parameter xpar and starting averaging expression yexpr
tmin - minimal time to average expression yexpr
tmax - maximal time to average expression yexpr. Even if accuracy is less than yeps 
        averaging will stop
        
Function returns list of [x,y] pairs
```

- virtual Node 

phase source & mind

