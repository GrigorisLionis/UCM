# UCM
UCM is an acronym for the **UnContolled Manifold concept**, which is a hypothesis on how the redundant kinematic mechanism of the human body moves.
The scope of this project is to implement the **UCM** apporoach on **real human walking** motion data. This work is executed under contract for a  research group.
## A -very- short description of UCM
UCM is a theoretical concept [^1] that essentially states that during a motion task where the human body controls a specific control variable in the task space , **most** of the joint variance belongs to the **null space** of the kinematic chain wrt this  specific control variable and the nominal position. Obviously, this definition makes sense only when the task is *repeated* or where there is a naturally defined nominal position in the task space. (otherwise there is no notion of variance)
Mathematically, if $v$ is the control variable (in a suitable task space) and $q$ is the configurarion vector, $$v=F(q)$$
[^1]:J.Scholz&G.Schöner,The uncontrolled manifold concept: identifying control variables
for a functional task,Experimental Brain Research,1999,v126,289-306
## Implementing the UCM approach
We are tasked to implement the UCM algorithm for a human walking task, and we are given the joint coordinates wrt -normalized- time, and a set of potential control varibles in the task space. 
To solve the problem of implenenting the algorithm,  we use sympy toolbox to create a **symbolic representation** of the human lower kinematic chain. The code produces internally a anayltic model of the kinematic position of the body wrt the joint angles. Alternatively we could have used the python robotics toolbox which contains relevant functionality,but we opted for using sympy to have more direct control of the symbolic model produced.
### Algorithm for UCM calculations for human walk experiments
* select control variable & construct symbolic representation of the Jacobian
* select/construct nominal trajectory
* compute the Jacobian for points on the nominal trajectory
* for each trajectory, and each point
  * compute deviation of joint vector from nominal position
  * decompose vector on null space and on orthogonal to null
  * compute measure of the two vectors
* compute statistics of vector measures    

In the followinng figure,
![](https://github.com/GrigorisLionis/UCM/blob/main/file01.png)
a depiction of the output of the  symbolic model output is shown. The model uses a 3DOF pelvis, and 3DOF for each leg segemt resulting into a 21DOF complete model. (each joint, hip, knee and ankle was modelled as a 3DOF ball and socket joint). The image depicts the lower kinematic chain in 3D and in the two frontal and saggital  planes. The origin is on the left end of the pelvis.
The symbolic model allowed for easy implementation of the basic theory behind UCM,  for investigating the validity of the concept for different control variables. As UCM essentialy lies on **computing the jacobian of the kinematic chain** and projecting the  joint variance on the null space wrt to a workspace control variable, a symbolic model, along with the extra powerfull symbolic capabilities of sympy, allows for an easy implementation of the UCM algo. 

### Results
In the following figure, 

![](https://github.com/GrigorisLionis/UCM/blob/main/traj.jpeg)

a plot of the varianace of a specific control variable wrt the normalized time (s) , for a number of different runs (r) is depicted, showing the variability of the motion.  

While in the following figure,

![](https://github.com/GrigorisLionis/UCM/blob/main/results.png)

a composite plot depicting different aspects of the variance (V4,V5,V6) are shown wrt normalized time (X axis, V2) , for different control variables (X facet)  and different walking conditions (color coded) 

### Disclaimer
This work is under contract for a research group analyzing specific data, so **code, data and results** are copyrighted. Images are depicted only for indicative demonstration of results.  
