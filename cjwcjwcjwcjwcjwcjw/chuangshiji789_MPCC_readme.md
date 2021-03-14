# MPCC
Simulation environments in C++ and Matlab of the Model Predictive Contouring Controller (MPCC) for Autonomous Racing developed by the Automatic Control Lab (IfA) at ETH Zurich

## Fromulation

The MPCC is a model predictive path following controller which does follow a predefined reference path X^ref and Y^ref. This is achieved by augmenting the system with an integrator stated theta which approximates the progress along the reference path. The theta state is coupled to the real dynamics using the lag error e^l which is penalized in the cost. Additionally, the contouring error (lateral error to the reference path) is also penalized in the cost function. Finally, the progress along the reference path is maximized to achieve that the car does follow the path as fast as possible and the rate of the inputs is penalized. To guarantee that the car stays within the track, track constraints are imposed as well as bounds on all states, inputs and the rate of inputs. The resulting optimization problem is shown in the following equation:
 

The vehicle dynamics considered is a bicycle model with nonlinear magic formula tire models:
 

with the tire model and drive train model given as follows:
 

Finally, the state and inputs of the problem are given as follows:
 

Where (X,Y) is the global position phi the heading of the car, v_x and v_y the longitudinal respectively the lateral velocity and omega the yaw rate. Theta is the augmented state which approximates the progress. The inputs are the duty cycle d to the drive train, the steering angle delta and the velocity along the reference path v_theta (which is an approximation of the velocities projected onto the path)

To achieve obstacle avoidance of other cars, before solving the MPCC problem grid search 1-D dynamic programming approach finds the best way to avoid the obstacles. This path is then converted into a corridor which modifies the track constraint. 

Finally, to solve the MPCC problem, we approximate the nonlinear problem as a time-varying quadratic program, by linearizing and discretizing the dynamics, approximating the lag and contouring errors using a first order Taylor approximation and approximating the track constraints with two linear half space aligned with the boundaries. The resulting quadratic program is then solved using [hpipm](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b0e80a74af22b7f9356a7b53d8f3548f), however the matlab implementation also offers a Yalmip, CVX, and direct QuadProg interface.

Note that the C++ implementation has some additional features proposed in the following paper [AMZ Driverless: The Full Autonomous Racing System](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa05754b20c2d234b32c05dd4b5f89942bd2447). However, obstacle avoidance is currently only supported in the Matlab implementation.

For more details see our paper [Optimization‐based autonomous racing of 1:43 scale RC cars](http://u.720life.cn/g/aa4bd6a6884c1430ee2e9259bd8c8e378ca5c7e64a219d976503ed4bc95cc51b76d7f11bd966f1e5d3fafac755616e3efdad2b0851667cab79c4b7264daaba8b) or the [Arxiv](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa05754b1860d2bd516395e8226dff8506c56ec) version.

## How to run
See the individual instruction for the C++ and Matlab code in the respective folders.

## Example
 

## Papers
If you use the C++ or Matlab code please cite 
- [Optimization‐based autonomous racing of 1:43 scale RC cars](http://u.720life.cn/g/aa4bd6a6884c1430ee2e9259bd8c8e378ca5c7e64a219d976503ed4bc95cc51b76d7f11bd966f1e5d3fafac755616e3efdad2b0851667cab79c4b7264daaba8b)

and if you use the C++ version please also
- [AMZ Driverless: The Full Autonomous Racing System](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa05754b20c2d234b32c05dd4b5f89942bd2447)

## Related Papers for the interested reader
### Optimization‐based autonomous racing of 1:43 scale RC cars
Liniger, A., Domahidi, A. and Morari, M.  
Optimization‐based autonomous racing of 1: 43 scale RC cars.  
Optimal Control Applications and Methods, 2015, 36(5), pp.628-647. 


Explains the MPCC problem for autonomous racing and the obstacle avoidance approach, as described above.

### Efficient implementation of randomized MPC for miniature race cars
Carrau, J.V., Liniger, A., Zhang, X. and Lygeros, J.  
Efficient implementation of randomized MPC for miniature race cars.  
2016 European Control Conference (ECC).


Shows how to implement an efficient sampling based randomized MPC approach using the MPCC approach. First, the track constraints can be reformulated as chance constraints, and approximated using randomized MPC. We then show that the problem can be split in a constraint tightening pre-processing step and solving a deterministic MPC problem with tight-end constraints. The advantage of this two step approach is that it only causes an overhead in the order of few milliseconds.

### Racing miniature cars: Enhancing performance using stochastic MPC and disturbance feedback
Liniger, A., Zhang, X., Aeschbach, P., Georghiou, A. and Lygeros, J.  
Racing miniature cars: Enhancing performance using stochastic MPC and disturbance feedback.  
2017 American Control Conference (ACC).


Similar to the previous paper, the MPCC is augmented with probabilistic track constraints, and we show that it is beneficial to optimize over the feedback policies used in stochastic MPC, using the disturbance feedback approach. We also show that by using only 3 samples, the approach can be implemented in real-time and that even when using so few samples, it helps on the experimental platform.

### Cautious NMPC with gaussian process dynamics for autonomous miniature race cars
Hewing, L., Liniger, A. and Zeilinger, M.N.  
Cautious NMPC with gaussian process dynamics for autonomous miniature race cars.  
2018 European Control Conference (ECC).


This paper proposes to learn the model mismatch between the real car and the MPC model using Gaussian Processes (GP). The GP is then considered when solving the MPC problem which helps to improve the performance. Furthermore, is the uncertainty in the GP considered by using probabilistic track constraints. The approach shows good results in simulation when the simulation model had a savier model mismatch.

### Learning-based model predictive control for autonomous racing
Kabzan, J., Hewing, L., Liniger, A. and Zeilinger, M.N.  
Learning-based model predictive control for autonomous racing.  
IEEE Robotics and Automation Letters, 2019, 4(4), pp.3363-3370.


This paper uses the previous paper as a basis but implements the approach on the AMZ Formula Student car. Additionally, online learning is implemented using a dictionary that is automatically updated based on how informative a data point is for the GP. The approach was tested on the real Formula Student car and reduced the lap time by 10% once the GP dictionary had converged.

### AMZ Driverless: The Full Autonomous Racing System
Kabzan, J., et. al.  
AMZ Driverless: The Full Autonomous Racing System.  
arXiv preprint arXiv:1905.05150, 2019.


This paper explains the full system used in the AMZ Driverless car for the 2017 and 2018 seasons. This also includes the MPCC including new features added in the C++ implementation of this GitHub repo, mainly the tire constraints and side slip angle cost. However, the paper also proposes a interesting mixed kinematic-dynamic model, which allows to get the benefits of kinematic models at slow speeds and the accuracy of dynamic models at high speeds.




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0d7b6c1dd68fd1018593cc0a20ed03c9fd59a4ade03046b9a2265fd35c737e015f49db6aae352c5b1318651f1dd0a269)