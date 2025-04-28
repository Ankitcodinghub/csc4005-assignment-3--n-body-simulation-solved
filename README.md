# csc4005-assignment-3--n-body-simulation-solved
**TO GET THIS SOLUTION VISIT:** [CSC4005 Assignment 3- N Body Simulation Solved](https://www.ankitcodinghub.com/product/csc4005-assignment-3-n-body-simulation-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;118013&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSC4005  Assignment 3- N Body Simulation Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
&nbsp;

Abstract

This assignment implements a N body problem, using 4 versions – one sequential method and 3 parallel methods, namely the MPI method, pthread method, and openmp method. The report will present the principle, codes, as well as comparasion and analysis of performance of different implementations.

1. Introduction

The N Body problem refers to the problem of predicting the motion of n celestial bodies that interact gravitationally. Numerical methods must be used to simulate such systems. Initially, the bodies are listed in random places in a 2D space. The gravity between

N-body is : .

Here are some assumptions about the collision and bouncing:

1. The display size is 200×200, and iteration number is 100 for all cases.

2. When a body goes to the edge of the display, it will change the direction so as to keep within the 200×200 display. For example, when a point goes right to the edge of x axis, it will turn left with the same velocity.

3. When two bodies have a collision, it will not produce small bodies, and we simply assume that nothing else happens.

The following Figure 1 is a screenshot during the simulation with display size 200 × 200.

Figure 1. caputre of N body simulation by X11

The implentation details and performance analysis are shown below.

2. Method

For all methods, we use For parallel methods, we use the number of processes or threads ranging from 1 to 16.

2.1. Sequential

At one time stamp, need to calculate the force of each body with all other bodies, then get the acceleration, then get the velocity and the new position by numerical method. (Here, we set the ∆t to be 0.01).

then, we can get the new velocity

then we can update the new position (in both xx

and y axis) xt+1 = xt + v∆t

The psudocode is shown in the following:

for t = 1··· ,iteration do for i = 0 : num_bodies − 1 do

F = Force_routine(i); v[i]_new = v[i] + F · dt/m; x[i]_new = x[i] + v[i] · dt;

end for for i = 0 : num_bodies − 1 do update velocity; update poosition; end for

end for

Initialize all body forces to be 0.

for i = 0 : num_bodies − 1 do

for j = i + 1 : num_bodies − 1 do

F[i] + = Force_between(body[i],body[j]); F[j] − = Force_between(body[i],body[j]); end for

end for

Data Structures: We define three data structures in the code: Body(contain x, y, and mass); Force(contain Fx, Fy), and Velocity(contain Vx, Vy) for simplier representation of 2D graph. All the instances are in DOUBLE format.

2.2. OpenMP

In the sequential method, there are two for loops in each iteration. One is for calculating the force and velocity for each body, and another is for updating the location and velocity. Then we can add ”#pragma omp parallel for” before each for loop.

The flow chart is shown in Figure 2.

Figure 2. Flow chart for OpenMP implementation

2.3. MPI

In the MPI implemantation, assume there are n nodies and k processes including the MASTER node.

1. First attribute the part to each node, calculate the forces and velocities.

2. Second do the computation for the extra parts n%k on MASTER.

During each iteration, we need MPI_Bcast to synchronize all bodies’ position and mass. Then in each process, do the calculation for force and velocities of bodies. Do the calculation for force and velocities of n%k bodies on MASTER. Then use MPI_Allreduce to synchronize bodies’ position in each slave node, and use MPI_Bcast again to synchronize the n%k bodies on MASTER to all slaves.

Since the MPI version needs extra communication costs, the method of calculating all body forces without exhausting calculation is hard to implement. We just calculate the force between each body with all other bodies.

The flow chart is shown in Figure 3 .

Figure 3. Flow chart for MPI implementation

2.4. Pthread

Since all threads can work in parallel, here we adopt the number of threads ranging from 1 to 16 in the experiment. The program is flexible for different inputs of thread numbers, and bodies. Just like the MPI version, we distribute data to each threads with bodies to compute, but the last thread contains bodies.

In the implementation, pthread_barrier_init(barrier) is used to maintain each thread’s pace, in order to finish one iteration. Global variable bodylist, newblist, vellist, newvlist are used to record and update the position and velocity of bodies after each iteration.

Figure 4 shows the flow chart of Pthread method.

Figure 4. Flow chart for Pthread method

Remark: for drawing the program, when it comes to the second pthread_barrier_wait in one iteration, we can add one barrier wait in the master process. Then we can conduct drawing in master for each iteration.

2.5. Command lines

All the heigh and width in the display are 200 by default. For the MPI program, the first instance of main function is number of bodies. For Openmp programs, the first instance is number of threads(default is 1) and the second instance is number of bodies. For pthread program, the first instance is number of threads(default is 1), and the number of bodies needs to change the variable in the file.

In order to evaluate the performance namely runtime, the drawing procedure is not included in the parallel programs. However, the ”seq_draw.cpp” indicates a sequential version with the X11 drawing procedure. And a video recording the simulation is attached in the package.

The sample compile codes are listed below: #Sequential g++ ./seq.cpp -o ./seq -lX11

./seq 800

#MPI

mpic++ ./mpi.cpp -lX11 -o ./mpi mpirun -n 8 ./mpi 800 #Pthread

g++ ./pth.cpp -o ./pth -lpthread -lX11

./pth 8

#OpenMP

g++ -o ./openmp ./openmp.cpp -fopenmp

./pth 8 800

3. Experiment

The most important metric here is runtime under different circumtances. Since the X11 drawing procedure is slow, here we only consider the computation runtime, including the data transmiting, and without displaying the graph. The total results are attatched in Appendix A. One important figure that consolidates all usful information in performance is shown in Figure 5. The red horizontal line in the figure refers to the sequential implementation time (calculated by the average of 5 times).

Figure 5. Performance comparasion figure.

Sections below are several analysis based on different evaluation metrics:

3.1. The number of processes or threads used in theprogram

3.2. The number of bodies ranging from 200, 800,2000, to 5000

Figure 6. Average running time VS number of bodies.

The number of bodies in the system greatly influences the time for data processing. As shown in Figure 6, as the number of bodies increases, the running time also increases. It shows a convex function trend and the increase rate in time versus body number is the biggest for sequential work, then for Pthread, then OpenMP, at last MPI. MPI runtime increases really small comparing to the other three methods.

3.3. MPI vs Sequential vs Pthread vs OpenMP

With the study with different metrics, we can say that the MPI method performs really well, with nearly 4 nodes to be the best option. All three methods would not have greater speed up when processors become more than 6-8.

Generally, MPI implementation is good for larger size of data. As data size goes up, it would have a better effciency, and it performs more stable for large number of processors.

Overall, the parallel method performs better than sequential method. Here is also an analysis of efficiency for different methods theroically(omit the transmission time):

Sequential: under each iteration: O(n2); total:

O(m · n2), where m is the number of iterations. Parallel: under each iteration: ;

total:

4. Conclusion and Reflection

In this experiment, 3 parallel versions of N body Problem is conducted with pthread, MPI, and OpenMP approach. The results shows that generally as the number of threads or processes increases, the total time for the problem will decrease. After 8 nodes, the performance would not have a big speed up. And the number of bodies determines generally how much time a sequential version could be used. As the size of figure increases, the time needed increases as well. Also, the best version is the MPI parallel version, normally with 4 processes.

Through this project, I understand more about the implementation details of different parallel methods, and trained my X11 implementation as well. Since one task is only limited to 5 min on the server, it would be better if I can find thhe running time for Pthread, 5000 bodies or larger if time permits. OpenMP+MPI methhod also needs more digging.

A. Experiment Results

The total results are listed in Figure 7. Focus on runtime for each case.

1

num_bodies

method

Sequential

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

MPI

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

Pthread

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP

OpenMP process 200 800

8.064199

3.67086 1.94913 1.28626 1.23017

3.58089

4.9552

3.68956 2.78559 3.15581 3.40343 3.62112 2.79426 2.92653 5.60511

2.92596

2.5325

12.53905

9.10933 5.98104 3.63162 3.83432

3.48015

4.2092

3.57593 3.53097 3.54023 3.61254 3.77262 3.77987

3.75693

3.531

3.5885

3.83754 5.27477 4.89286 4.39321

4.33929

4.4495

4.5613

4.94593 4.08713 4.90584 3.89418 4.41612 4.05506

4.41763

4.5843

5.25995 2000

44.577399

18.72262

11.19838

8.50533

7.09912

11.36644 11.37187

10.97583

9.30494 9.18108 8.30846

8.32321

7.2943

7.27868

6.6145

6.48221 5.89102

79.83276

45.23536

30.6123

27.44217 19.62874 24.45099 21.56743 18.56438

18.66904

17.5046

17.48104 17.06076 41.19403 23.70812 21.97542

25.08728

23.4094

25.78404 24.45077 27.15419 25.73201 25.32849 26.82351 31.68013 26.33266 26.67821

30.68288

23.4694

23.45593 29.61361 23.43605

24.86235 5000

255.027984

147.04071

67.49418 45.56408 37.82939 27.52291 38.86694 36.32744 33.44564

30.12844

30.0228

28.95005 23.53277 23.25591 20.81836

19.84742 18.1489

137.78547

172.37507

165.40293

144.42339

167.84307

151.07292

150.09084

140.11702

179.85084

183.94087

147.63798

173.90883

194.22293

198.3523

160.15953 163.8167

1

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16 0.645882

0.2981

0.15543 0.11652 0.09284 0.64013 2.08806 1.54778 1.24449 1.06947 0.83531 1.88236 1.06833 0.85489 1.20559 0.70487 1.80682 0.98586 0.52076 0.36487 0.28334 0.26642 0.29691 0.27698

0.23811

0.2354

0.21427

0.24177

0.3293

0.27209 0.25214 0.27292 0.23557 0.29904 0.36739 0.27437 0.26668 1.09712 0.30273 0.29416 0.22294 0.32342

0.30674

0.3491

0.36647 0.31859 0.34322 0.26923

0.26956

result.xls

Figure 7. Overall result

B. Codes

All codes, video, analysis codes, can be found in the folder attached. On the server, the codes are just in /home/117010038.
