# NetPractice
This project is a general practical exercise to let you discover networking

## Level 1

You have **two separate networks** with different subnet masks:

1. **Network 104.95.23.0/24**
    - Host A (your PC) with interface **A1 (104.95.23.10)**
    - Host B (your brother) with interface **B1 (104.95.23.12)**
    - **Mask**: `255.255.255.0` → This is a subnet with 256 addresses.
2. **Network 211.191.0.0/16**
    - Host C (your Mac) with interface **C1 (211.191.250.75)**
    - Host D (your sister) with interface **D1 (211.191.250.15)**
    - **Mask**: `255.255.0.0` → This subnet allows more addresses because it uses /16.

---

## 🔹 **How packets travel**

The data traffic follows this flow:

### 🔸 **Case 1: Communication A → B**

1. A receives a packet for **104.95.23.12 (B)**
2. A checks its routing table:
    - It sees that **104.95.23.12 is in its same subnet (104.95.23.0/24)**.
    - It sends the packet directly to **B1** without needing a router.
3. B receives the packet and responds to **104.95.23.10 (A)** in the same way.

✅ **It works because A and B are in the same subnet and can communicate directly.**

---

### 🔸 **Case 2: Communication C → D**

1. C receives a packet for **211.191.250.15 (D)**
2. C checks its routing table:
    - It sees that **211.191.250.15 is in its same subnet (211.191.0.0/16)**.
    - It sends the packet directly to **D1**.
3. D receives the packet and responds to **211.191.250.75 (C)** in the same way.

✅ **It works because C and D are in the same subnet and can communicate directly.**
