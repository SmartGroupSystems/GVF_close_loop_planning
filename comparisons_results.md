
# Quantitative Comparison under Disturbances

We compare the proposed GVF-based method with the Fast Planner and its recoverable variant under disturbance conditions.

---

## Fast Planner

<p align="center">
  <img src="./figures/fast-pos.png" width="70%">
  <img src="./figures/fast-vel.png" width="70%">
  <img src="./figures/fast-wind.png" width="70%">
</p>

F1: Position tracking performance of the Fast-Planner under disturbance.

F2: Velocity profile of Fast-Planner under disturbance. Taking the Y-axis velocity in the time interval from 15\,s to 20\,s as an example, the actual velocity of the quadrotor exhibits fluctuations due to wind disturbances, while the reference velocity does not provide corresponding compensation. This leads to a gradual accumulation of tracking error and eventually results in navigation failure.

F3: Wind disturbance profile experienced by Fast-Planner during flight, where the disturbance follows a sinusoidal pattern.

<p align="center">
  <img src="./figures/fast-sim1.png" width="75%">
  <img src="./figures/fast-sim2.png" width="75%">
</p>

The original Fast Planner exhibits significant trajectory deviation and lacks effective recovery under disturbances.

---

## Fast Planner (Recoverable)

<p align="center">
  <img src="./figures/fastre-pos.png" width="70%">
  <img src="./figures/fastre-vel.png" width="70%">
  <img src="./figures/fastre-wind.png" width="70%">
</p>

<p align="center">
  <img src="./figures/fast-recover-sim1.png" width="75%">
  <img src="./figures/fast-recover-sim2.png" width="75%">
</p>

The recoverable Fast Planner improves disturbance handling but still suffers from discontinuities and delayed recovery.

---

## GVF (Proposed Method)

<p align="center">
  <img src="./figures/gvf-pos.png" width="70%">
  <img src="./figures/gvf-vel.png" width="70%">
  <img src="./figures/gvf-wind.png" width="70%">
</p>

<p align="center">
  <img src="./figures/gvf-sim1.png" width="75%">
  <img src="./figures/gvf-sim2.png" width="75%">
</p>

The proposed GVF-based method achieves smooth and continuous trajectory adaptation, demonstrating superior robustness under disturbances.

---

## Summary

Compared with both Fast Planner and its recoverable variant, the GVF-based method provides continuous feedback-driven navigation, avoids abrupt replanning behavior, and enables faster and smoother recovery under disturbances.
