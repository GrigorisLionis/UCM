### UCM
UCM is an acronym for the UnContolled Manifold concept, which is a hypothesis on how the redundant kinematic mechanism of the human body moves.
The scope of this project is to implement the UCM apporoach on real human motion data, working for a research group analyzing specific data. 
## A short description of UCM
## Implementing the UCM approach
To solve the problem of implenenting the algorithms,  we used sympy toolbox to create a symbolic representation of the low kinematic chain. Alternatively we could have used the python robotics toolbox,but we opted for using sympy to have more direct understanding of the symbolic model produced.

The symbolic model allowed for easy implementation of the basic theory behind UCM, and for investigating the validity of the concept for different control variables.

In the following figure, 
![](https://github.com/GrigorisLionis/UCM/blob/main/traj.jpeg)

a plot of the varianace of a control variable, for a number of different runs is shown.  
