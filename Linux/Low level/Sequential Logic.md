

## Active high Rs NOR Latch

---

![2023-02-01-220440_225x163_scrot.png](2023-02-01-220440_225x163_scrot.png)

![2023-02-01-220709_734x226_scrot.png](2023-02-01-220709_734x226_scrot.png)

### Active low Rs NAND Latch

---

![2023-02-01-222421_254x183_scrot.png](2023-02-01-222421_254x183_scrot.png)

![2023-02-01-221246_740x234_scrot.png](2023-02-01-221246_740x234_scrot.png)

### Gated RS Latch

---

It is like an Active high RS NOR Latch but with an switch just before 

![2023-02-01-222315_397x201_scrot.png](2023-02-01-222315_397x201_scrot.png)

![2023-02-01-222320_707x285_scrot.png](2023-02-01-222320_707x285_scrot.png)

### Positive-Edge-Triggered RS Flip-Flop

---

This is a RS Latch changing only when C gets from 0 to 1

![2023-02-01-222549_670x204_scrot.png](2023-02-01-222549_670x204_scrot.png)

![2023-02-01-222804_702x210_scrot.png](2023-02-01-222804_702x210_scrot.png)

### Negative-Edge-Triggered RS flip-flop

---

The same as before except that it changes when C is going from 1 to 0.

![2023-02-01-222953_674x206_scrot.png](2023-02-01-222953_674x206_scrot.png)

### Master-Slave RS flip-flop

---

When C goes up, the values of S and R are memorized, but Q will be affected only when C will get down.

![2023-02-07-125845_1245x542_scrot.png](2023-02-07-125845_1245x542_scrot.png)

![2023-02-01-223547_590x201_scrot.png](2023-02-01-223547_590x201_scrot.png)

## Gated D latch

---

![2023-02-07-125341_905x445_scrot.png](2023-02-07-125341_905x445_scrot.png)

The gated D latch is this : 

$E = 1 \implies Q = D$

otherwise nothing changes

It is represented as such :

![2023-02-07-125553_329x242_scrot.png](2023-02-07-125553_329x242_scrot.png)

Everything else in the D category is just a derivation of this circuit.

### positive-edge-triggered D flip-flop

---

![2023-02-07-125729_1053x259_scrot.png](2023-02-07-125729_1053x259_scrot.png)

### negative-edge-triggered D flip-flop

---

![2023-02-07-125754_1062x247_scrot.png](2023-02-07-125754_1062x247_scrot.png)

### master-slave D flip-flop

---

![2023-02-07-130050_1047x264_scrot.png](2023-02-07-130050_1047x264_scrot.png)

## The JK flip-flop

---

The JK flip-flop allows us to have more control over the circuit : 

![2023-02-07-131058_875x509_scrot.png](2023-02-07-131058_875x509_scrot.png)

![2023-02-07-131428_1048x587_scrot.png](2023-02-07-131428_1048x587_scrot.png)

put another way :

 

![2023-02-07-131140_1330x401_scrot.png](2023-02-07-131140_1330x401_scrot.png)

Again, everything else in the D category is just a derivation of this circuit.

### Negative-edge-triggered JK flip-flop

---

![2023-02-07-131234_1360x404_scrot.png](2023-02-07-131234_1360x404_scrot.png)

### Master-slave JK flip-flop

---

![2023-02-07-131323_1350x423_scrot.png](2023-02-07-131323_1350x423_scrot.png)