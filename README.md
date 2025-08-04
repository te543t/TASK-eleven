# Robot Arm Torque Calculation and Motor Selection

## 📐 Arm Specifications
- First link length: 15 cm (0.15 m)
- Second link length: 10 cm (0.10 m)
- Third link (end effector) length: 4 cm (0.04 m)
- Payload at the end of the arm: 1 kg (with possibility of increasing to 2 kg)

---

## 📝 1) Calculating Required Torque for Each Joint

### Force due to payload
- For 1 kg:
  ```
  F = mass × gravity = 1 kg × 9.81 m/s² = 9.81 N
  ```
- For 2 kg:
  ```
  F = 2 kg × 9.81 m/s² = 19.62 N
  ```

---

### Joint 3 (last joint, at the end effector):
- Distance from joint to payload: 0.04 m  
- Torque required for 1 kg:
  ```
  T3 = 9.81 N × 0.04 m = 0.3924 N·m
  ```
- Torque required for 2 kg:
  ```
  T3' = 19.62 N × 0.04 m = 0.7848 N·m
  ```

---

### Joint 2 (middle joint, 10 cm link):
- Distance from joint to payload: 0.10 + 0.04 = 0.14 m  
- Torque required for 1 kg:
  ```
  T2 = 9.81 N × 0.14 m = 1.3734 N·m
  ```
- Torque required for 2 kg:
  ```
  T2' = 19.62 N × 0.14 m = 2.7468 N·m
  ```

---

### Joint 1 (base joint, 15 cm link):
- Distance from joint to payload: 0.15 + 0.10 + 0.04 = 0.29 m  
- Torque required for 1 kg:
  ```
  T1 = 9.81 N × 0.29 m = 2.8449 N·m
  ```
- Torque required for 2 kg:
  ```
  T1' = 19.62 N × 0.29 m = 5.6898 N·m
  ```

---

## 🔎 2) Can the Same Motors Lift 2 kg?

- If you use the same motors selected for lifting 1 kg, they will be **underpowered** if you switch to lifting 2 kg — you would need roughly double the torque.
- **Solution with gears:** You can add gear reduction (e.g., 2:1 ratio) to double the torque at the joints using the same motors.
- **Drawbacks of using gears:**
  - Slower movement due to speed reduction.
  - Increased friction, mechanical complexity, and potential backlash.
  - Heavier and larger arm design.

---

## ✅ Alternatives to Avoid Drawbacks
- Choose motors with higher torque ratings instead of relying heavily on gears.
- Use lightweight materials (carbon fiber, aluminum) to reduce required torque.
- Optimize arm design to move the center of mass closer to the joints, minimizing torque requirements.

---

## 🛒 Suggested Motors (for 1 kg payload with safety margin ~20%)
- **Joint 1:** Dynamixel MX-64T (6 N·m)
- **Joint 2:** Dynamixel AX-18A (1.8 N·m)
- **Joint 3:** Dynamixel AX-12A (1.5 N·m)

### Links to purchase:
- [Dynamixel MX-64T](https://www.robotis.us/dynamixel-mx-64t/)
- [Dynamixel AX-18A](https://www.robotis.us/dynamixel-ax-18a/)
- [Dynamixel AX-12A](https://www.robotis.us/dynamixel-ax-12a/)

---
