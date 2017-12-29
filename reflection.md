# Reflection

## Effect of P, I, D components on the steering angle controller
 
### P: 

* Helps steer in proportion to the crosstrack error
* Accounts for current values of error.

Model value: P = 0.1

| Param state        | Description           |
| ------------- |:-------------:|
| Higher P, P = 0.7      | Sharp turns, controller is super sentsitive to the errors. The controller has a large amount of overshoot. |
| Lower P, P = 0.0005      | Immediately went off the track during the initial straight road portion. The time constant is too high.      |


### I: Integral

* Help adjust systematic bia (system error due to calibration or hardward deficit).
* Adjust the cumulated error over time.

Expected optimal value is low because we don't expect wheels in the simulator to be misaligned much.

Model value: I = 0.01

| Param state        | Description           |
| ------------- |:-------------:|
| Higher I, I = 0.2      | Over-accounts for bias and immediately veers off. |
| Lower I, I = 0      | Car position seems slightly shifted      |

### D: 

* This overcomes overshoot since it accouts for the changing of the direction and the changing rate.

Model value: D = 4.5


| Param state        | Description           |
| ------------- |:-------------:|
| Higher D, D = 5.0      | Counter-steers too much. |
| Lower D, D = 2.0      | Overshoot      |


### How the final hyperparameters were chosen

The final hyperparameters (0.12, 0.002, 4.3) were tuned manually.

### References:
* [PID Controller (Wikipedia)](https://en.wikipedia.org/wiki/PID_controller)
