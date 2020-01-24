## Self-Driving Car Engineer Nanodegree Program

## PID Controller

### Project Description

My goal for this project was effectively implement PID controllers to avoiding pop up onto ledges or roll over any surfaces while driving. Therefore I used steering angle control and speed control as PID controls. *Steering angle control* uses cross track error as an input and produces the correcting steering angle, *Speed Control* uses speed error as an input and produces the correcting throttle value.

**P -** The "**Proportional**" part makes the car steer in proportion to the cross track error. In other words, it steers the car along to road center. The proportional factor `Kp` is multiplied by the CTE to calculate the steering angle. Increasing `Kp` will make the the vehicle to oscillate faster which finally cause the car crashes or leaves the road.

**I -** The "**Integral**" part corrects systemic bias such as steering drift. It is responsible for compensating the bias that the car's steering wheel might have. The steering drift is not an issue in the simulation. When this component used alone, the car leaves the road and starts the circular motion.

**D -** The "**Differential**" part makes the steering angle to decrease as it reaches the reference trajectory. This allows the car to approach the trajectory "gracefully" rather than oscillating wildly. When this component used alone, the car is irresponsive to the road steepness and reacts only to little changes in the steepness.

I initially started with (0.2,0.004,3.0) for the steering control and (0.1,0.0,0.0) for speed control. All parameters adjusted manually. You can see final parameters below:

|      | Steering | Speed |
| ---- | -------- | ----- |
| Kp   | 0.13     | 0.1   |
| Ki   | 0.0      | 0.002 |
| Kd   | 3.0      | 0.0   |

The final hyperparameters let the vehicle stay on track between 30 mph and 40 mph. A little bit of fine tunning could make the vehicle go in track for higher speeds, but I would loose turning stability for the 30 mph

