# Analysis of P, PI and PID Controllers using MATLAB
## Aim:
To analyse the effect of P, PI and PID controllers for the system having open loop transfer function, G(S)=1/(S^2+10S+20) using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
	A controller is a device introduced in the system to modify the error signal and to produce a control signal. 
	The way the controller produces the control signal is called the control action.

Consider the following unity feedback system,
 <img width="823" height="281" alt="image" src="https://github.com/user-attachments/assets/36e49512-cf47-4fec-b00c-f79dc0af1c5f" />

### Proportional (P) Controller:
The proportional controller produces an output, which is proportional to error signal.<br>
u(t)∝e(t) <br>
⇒u(t)=Kpe(t) <br>
Apply Laplace transform on both the sides - <br>
U(s)=KpE(s) <br>
U(s)/E(s)=Kp <br>
Therefore, the transfer function of the proportional controller is Kp.

### Proportional Integral (PI) Controller:
The proportional integral controller produces an output, which is the combination of outputs of the proportional and integral controllers. <br>
u(t)=Kp e(t)+Ki ∫e(t)dt <br>
Apply Laplace transform on both sides - <br>
U(s)=(Kp+Ki/s)E(s) <br>
U(s)/E(s)=Kp+Ki/s <br>
Therefore, the transfer function of proportional integral controller is Kp+Kis. <br>

### Proportional Integral Derivative (PID) Controller:
The proportional integral derivative controller produces an output, which is the combination of the outputs of proportional, integral and derivative controllers. <br>
u(t)=Kp e(t)+Ki ∫e(t)dt+ Kd (de(t)/dt) <br>
Apply Laplace transform on both sides - <br>
U(s)=(Kp+Ki/s+Kds)E(s) <br>
U(s)/E(s)=Kp+Ki/s+Kd s <br>
Therefore, the transfer function of the proportional integral derivative controller is Kp+Ki/s+Kd s

### Characteristics of Kp, Ki and Kd terms:

Increasing the proportional gain ( ) has the effect of proportionally increasing the control signal for the same level of error. The fact that the controller will "push" harder for a given level of error tends to cause the closed-loop system to react more quickly, but also to overshoot more. Another effect of increasing   is that it tends to reduce, but not eliminate, the steady-state error.
The addition of a derivative term to the controller ( ) adds the ability of the controller to "anticipate" error. With derivative control, the control signal can become large if the error begins sloping upward, even while the magnitude of the error is still relatively small. This anticipation tends to add damping to the system, thereby decreasing overshoot. The addition of a derivative term, however, has no effect on the steady-state error.
The addition of an integral term to the controller ( ) tends to help reduce steady-state error. If there is a persistent, steady error, the integrator builds and builds, thereby increasing the control signal and driving the error down. 
 


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the steady state error and analyse the controllers.
## Program: 
### Without Controller (Open loop System)
```num=[1];
den=[1 10 20];
sys=tf(num,den)
subplot(2,2,1)
step(sys)
title("o-l")
```

### With P-Controller
```Kp=200;
C1=pid(Kp);
f1=feedback(C1*sys,1);
subplot(2,2,2)
step(f1)
title("p-controller")
```

### With PI Controller
```Kp=200;
Ki=60;
C2=pid(Kp,Ki);
f2=feedback(C2*sys,1);
subplot(2,2,3)
step(f2)
title("pi-controller")
```
### With PID Controller
```Kp=200;
Ki=60;
kd=30
C3=pid(Kp,Ki,kd);
f3=feedback(C3*sys,1);
subplot(2,2,4)
step(f3)
title("pid-controller")
```
<img width="1917" height="1075" alt="image" src="https://github.com/user-attachments/assets/969fd14b-3d05-4523-b5dd-14768e57b494" />

## Output: 
### Without Controller (Open loop System)

<img width="900" height="512" alt="image" src="https://github.com/user-attachments/assets/c4a765a0-fa52-4c4d-affa-d2c703b79753" />


### With P-Controller
<img width="832" height="490" alt="image" src="https://github.com/user-attachments/assets/1e2d2093-d5ac-4df8-8104-11eeee4ef0c3" />

### With PI Controller
<img width="887" height="462" alt="image" src="https://github.com/user-attachments/assets/9c04f669-48c4-47d6-bf61-7898fc86aef2" />

### With PID Controller
<img width="861" height="453" alt="image" src="https://github.com/user-attachments/assets/dace123e-2d8c-4c37-8b1b-c049daaad6c6" />

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/ead74b63-19a7-4ce4-95bc-231c9702b083" />

## Result:
Thus the P, PI and PID controllers for the given system was analysed and the following conclusions were arrived using MATLAB. <br>
### With-out controller 
Delay time =         <br>
Rise time =             <br>
Peak time =           <br>
Settling time =            <br>
Steady State Error =        <br>
### With P Controller 
Delay time =         <br>
Rise time =             <br>
Peak time =           <br>
Settling time =            <br>
Steady State Error =        <br>
### With PI Controller 
Delay time =         <br>
Rise time =             <br>
Peak time =           <br>
Settling time =            <br>
Steady State Error =        <br>
### With PID Controller 
Delay time =         <br>
Rise time =             <br>
Peak time =           <br>
Settling time =            <br>
Steady State Error =        <br>




