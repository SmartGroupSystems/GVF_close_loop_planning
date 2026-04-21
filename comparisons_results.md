
# Quantitative Comparison under Disturbances

We compare the proposed GVF-based method with the Fast Planner and its recoverable variant under disturbance conditions.

---

## Fast Planner

<p align="center">
  <img src="./fast-pos.png" width="30%">
  <img src="./fast-vel.png" width="30%">
  <img src="./fast-wind.png" width="30%">
</p>

<p align="center">
  <img src="./fast-sim1.png" width="45%">
  <img src="./fast-sim2.png" width="45%">
</p>

The original Fast Planner exhibits significant trajectory deviation and lacks effective recovery under disturbances.

---

## Fast Planner (Recoverable)

<p align="center">
  <img src="./fastre-pos.png" width="30%">
  <img src="./fastre-vel.png" width="30%">
  <img src="./fastre-wind.png" width="30%">
</p>

<p align="center">
  <img src="./fast-recover-sim1.png" width="45%">
  <img src="./fast-recover-sim2.png" width="45%">
</p>

The recoverable Fast Planner improves disturbance handling but still suffers from discontinuities and delayed recovery.

---

## GVF (Proposed Method)

<p align="center">
  <img src="./gvf-pos.png" width="30%">
  <img src="./gvf-vel.png" width="30%">
  <img src="./gvf-wind.png" width="30%">
</p>

<p align="center">
  <img src="./gvf-sim1.png" width="45%">
  <img src="./gvf-sim2.png" width="45%">
</p>

The proposed GVF-based method achieves smooth and continuous trajectory adaptation, demonstrating superior robustness under disturbances.

---

## Summary

Compared with both Fast Planner and its recoverable variant, the GVF-based method provides continuous feedback-driven navigation, avoids abrupt replanning behavior, and enables faster and smoother recovery under disturbances.
