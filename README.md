# UCM
UCM is an acronym for the UnContolled Manifold concept, which is a hypothesis on how the redundant kinematic mechanism of the human body moves.
The scope of this project is to implement the **UCM** apporoach on **real human walking** motion data. This work is executed under contract for a specific research group.
## A -very- short description of UCM
UCM is a theoretical concept that essentially states that during a motion task where the human body controls a specific control variable in the task space , **most** of the joint variance belongs to the **null space** wrt this  specific control variable. Obviously, this definition makes sense only when the task is *repeated* (otherwise there is no notion of variance) 
## Implementing the UCM approach
We are tasked to implement the UCM algorithm fora human walking task, and we are given the joint coordinates wrt -normalized- time, and a set of potential control varibles in the task space. 
To solve the problem of implenenting the algorithm,  we use sympy toolbox to create a **symbolic representation** of the human lower kinematic chain. Alternatively we could have used the python robotics toolbox,but we opted for using sympy to have more direct understanding of the symbolic model produced.
The symbolic model allowed for easy implementation of the basic theory behind UCM,  for investigating the validity of the concept for different control variables. As UCM essentialy lies on **computing the jacobian of the kinematic chain** and projecting the  joint variance on the null space wrt to a workspace control variable, a symbolic model, along with the extra powerfull symbolic capabilities of sympy, allows for an easy implementation of the UCM algo. 

### Results
In the following figure, 

![](https://github.com/GrigorisLionis/UCM/blob/main/traj.jpeg)

a plot of the varianace of a control variable wrt the normalized time (s) , for a number of different runs (r) is shown.  

While in the following figure,

![](https://github.com/GrigorisLionis/UCM/blob/main/results.png)

a composite plot depicting different aspects of the variance (V4,V5,V6) are shown wrt normalized time (X axis, V2) , for different control variables (X facet)  and different walking conditions (color coded) 

### Disclaimer
This work is under contract for a research group analyzing specific data, so code, data amd results are copyrighted. Images are depicted only for indicative demonstration of results.  
