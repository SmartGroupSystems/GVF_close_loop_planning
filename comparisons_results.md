
# Quantitative Comparison under Disturbances

We compare the proposed GVF-based method with the Fast Planner and its recoverable variant under disturbance conditions.

---

## Fast Planner

<p align="center">
  <img src="./figures/fast-pos.png" width="70%">
  <img src="./figures/fast-vel.png" width="70%">
  <img src="./figures/fast-wind.png" width="70%">
  
  <em>Figure 1: Position, velocity, and wind disturbance responses of the UAV under the proposed method.</em>
</p>

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
