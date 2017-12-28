# Reflection

## Effect of P, I, D components on the steering angle controller
 
### P: 

* Helps steer in proportion to the crosstrack error
* Accounts for current values of error.

Model value: P = 0.1

<table>
	<th>Param state</th><th>Description</th>
	<tr>
		<td>Higher P,
		P = 0.7</td>
		<td>Sharp turns, controller is super sentsitive to the errors. The controller has a large amount of overshoot.</td>
	</tr>
	<tr>
		<td>Lower P, P = 0.0005</td>
		<td>Immediately went off the track during the initial straight road portion. The time constant is too high.</td>
	</tr>
</table>


### I: Integral

* Help adjust systematic bia (system error due to calibration or hardward deficit).
* Adjust the cumulated error over time.

Expected optimal value is low because we don't expect wheels in the simulator to be misaligned much.

Model value: I = 0.01
<table>
	<th>Param state</th><th>Description</th>
	<tr>
		<td>Higher I, I = 0.2</td>
		<td>Over-accounts for bias and immediately veers off.</td>
	</tr>
	<tr>
		<td>Lower I, I = 0</td>
		<td>Car position seems slightly shifted(e.g. red and white portions).</td>
	</tr>
</table>

### D: 

* This overcomes overshoot since it accouts for the changing of the direction and the changing rate.

Model value: D = 4.5

<table>
	<th>Param state</th><th>Description</th>
	<tr>
		<td>Higher D, D = 5.0</td>
		<td>Counter-steers too much.</td>
	</tr>
	<tr>
		<td>Lower D: D = 2.0</td>
		<td>THe overshoot is too large.
  </tr>
</table>

### How the final hyperparameters were chosen

The final hyperparameters (0.1, 0.01, 4.5) were tuned manually.

### References:
* [PID Controller (Wikipedia)](https://en.wikipedia.org/wiki/PID_controller)
