# ZMP-ZSLIP
> simplify z energy control & x y ZMP preview control

## 1. Method

**z spring model**

$$
-k(z - z_0) = m\ddot z
$$ 

$$
u = \frac{d\ddot z}{dt}
$$

where

$$
z_0 = z_{set} - \frac{mg}{k}
$$

so

$$
-k(z - z_{set}) = m(\ddot z + g)
$$

**x y zmp balance limitation => support is o**

with z spring model

$$
\frac{z}{g + \ddot z} = - \frac{m}{k} \frac{z}{z - z_{set}} 
$$

the xy balance

$$
p_x = x + \frac{z}{g + \ddot z} \ddot x
$$

so 

$$
p_x = x + \frac{m}{k} \frac{z}{z - z_{set}} \ddot x
$$

limitation

$$
P_{min} < p_x < P_{max}
$$

**simplify energy control**

z energy target

$$
E_1 (t = t1) -> E_2 (t = t1 + T)
$$

z control (circle to square):
* divide T into four parts, T starts from max z.
* t = -T/8 -> T/8  u -> 0
* t = T/8  -> 3T/8. if Et < Enow, track constant vzt. Else 0.

$$
vz_t =\sqrt{\frac{{E_t-E_{now}}}{m}}
$$

* t = 3T/8 -> 5T/8 u -> 0
* t = 5T/2 -> 7T/8. if Et > Enow, track constant vzt. Else 0.

$$
vz_t =-\sqrt{\frac{{E_t-E_{now}}}{m}}
$$


