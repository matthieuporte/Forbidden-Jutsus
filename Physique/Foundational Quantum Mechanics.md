#WIP 

Quantum Physics : rules and relations describing the physics of object at a subatomic scale (_aka. particles_).

#### Notation

>$\lambda$ = wavelength ($m$)
>$T$ = temperature ($K$)
>$f$ = frequency ($s^{-1}$)
>$E$ = energy ($J$)
>$<E>$ = average energy ($J$)
>$c$ = speed of light in free space ($m \cdot s^{-1}$)


![[ElectromagSpectrum.jpeg]]

##### Definitions
 - radiation : oscillating electromagnetic field
 - wavelength : distance traveled by wave in one period
 - black body : idealized, theoretical object that absorbs all incident electromagnetic energy perfectly

```functionplot
---
title: 
xLabel: Time (s)
yLabel: Electromag. field intensity
disableZoom: false
grid: false
---
sin(x) = 6sin(x/0.62831853071)
```

- period : length of time corresponding to one oscillation of a wave (equal to 4 seconds in the graph above)

#### Relations

>$\Large\lambda = \frac{c}{f}$
>$\Large \lambda_{max} = \frac{1}{T}$

---

## The ultraviolet catastrophe
Assuming a black body is in thermal equilibrium and has a uniform temperature, it emits radiation with on a spectrum of wavelengths at a certain intensity per wavelength given by the function $u(\lambda, T)$. We call this value value the **spectral energy density**

According to classical thermodynamics , the radiation emitted by a black body can be calculated by considering its molecules as small oscillators. Each one of these oscillators has a probability $P(E)$ to emit an energy $E$. In the domain of classical physics we _still_ consider that $E\in \left[ 0, \infty \right]$.

---
### Part 1 : Rayleigh-Jean's Implications

> Rayleigh Jean's law of radiation : $u(\lambda, T) = \Large\frac{8\pi}{c\lambda^{2}}<E>$ 
> [^1]: 

Here we calculate the average energy $<E>$ of the oscillator as follows.<br><br>
$$
\LARGE
<E>\;=\frac{\int_{0}^{\infty}P(E)\times E\;dE}{\int_{0}^{\infty}P(E)\;dE}
$$
<br>

$$
\LARGE
<E>\;=\frac{\int_{0}^{\infty} Ee^{-\frac{E}{k_{B}T}}\;dE}{\int_{0}^{\infty} e^{-\frac{E}{k_{B}T}}\;dE}
$$

> variable change : $x = \frac{E}{k_{B}T}$

<br>

$$
\LARGE
<E>\;=\frac{\int_{0}^{\infty} (x\times k_{B}T)\;e^{-x}\;(dx\times k_{B}T)}{\int_{0}^{\infty} e^{-x}\;(dx\times k_{B}T)}
$$
<br>

$$
\LARGE
<E>\;=\frac{(k_{B}T)^{2}\int_{0}^{\infty} xe^{-x}\;dx}{(k_{B}T)\int_{0}^{\infty} e^{-x}\;dx}
$$
<br>

For the sake of clarity we will split this form into the numerator integral $N$ and denominator integral $D$. In other words : $<E>=k_{B}T\times \frac{N}{D}$

---
$$
\LARGE
N = \int_{0}^{\infty}xe^{-x}\;dx
$$
<br>

$$
\LARGE
N = \int_{0}^{\infty}xe^{-x}\;dx
$$
> Hint : [[Integration by Parts]]
$$
\LARGE
N = \left[-e^{-x}\right]_{0}^{\infty}\;-\int_{0}^{\infty}-e^{-x}\;dx
$$
<br>

$$
\LARGE
N = \left[-e^{-x}\right]_{0}^{\infty}\;-\left[e^{-x}\right]_{0}^{\infty}
$$
<br>

$$
\LARGE
N = ((-e^{-\infty})-(-e^{-0})) - ((e^{-\infty})-(e^{-0}))
$$
<br>

$$
\LARGE
N = 0\;+\;1\;-0\;+1 = 2
$$
---

$$
\LARGE
D = \int_{0}^{\infty}e^{-x}\;dx
$$
<br>

$$
\LARGE
D = \left[-e^{-x}\right]_{0}^{\infty}
$$
<br>

$$
\LARGE
D = (-e^{-\infty})-(-e^{-0}) = 1
$$
#problem
---
Therefore, using the assumptions of classical physics, we come to the conclusion that the spectral energy density of the oscillator follows the relation : $u(\lambda, T) = \Large\frac{8\pi k_{B}T}{c\lambda^{2}}$. We can now calculate the total energy radiated by the black body : <br><br>

$$
\LARGE
U(\lambda,T) = \int_{0}^{\infty}u(\lambda,T)\;d\lambda
$$
<br>

$$
\LARGE
U(\lambda,T) = \int_{0}^{\infty}\frac{8\pi k_{B}T}{c\lambda^{2}}\;d\lambda
$$
<br>

$$
\LARGE
U(\lambda,T) = \frac{8\pi k_{B}T}{c}\times \int_{0}^{\infty}\frac{1}{\lambda^{2}}\;d\lambda
$$
<br>

$$
\LARGE
U(\lambda,T) = \frac{8\pi k_{B}T}{c}\times -\left[\frac{1}{\lambda}\right]_{0}^{\infty}
$$
<br>

$$
\LARGE
U(\lambda,T) = \frac{8\pi k_{B}T}{c}\times \infty
$$
<br>

So the oscillator (_aka._ molecule) has infinite energy... What?! Obviously this is not possible. This can only mean that classical physics has failed. We need to go deeper.

---

### Part 2 : Planck's new supposition

We will now take this problem from a new angle with Max Planck's idea of "quantization" of the black body's energy. The average energy $<E>$ is now calculated under the assumption that the energy of an oscillator can only have _discrete_ values (multiples of an elementary energy value $E_{0}$). 

>Planck's quantization law : $E = nE_{0},\; n\in \mathbb{N}$

<br>

$$
\LARGE
<E>\;=\frac{\sum_{n=0}^{\infty}\;P(nE_{0})\times nE_{0}}{\sum_{n=0}^{\infty}\;P(nE_{0})}
$$
<br>

$$
\LARGE
<E>\;=\frac{\sum_{n=0}^{\infty}\;nE_{0}e^{-\frac{nE_{0}}{k_{B}T}}}{\sum_{n=0}^{\infty}\;e^{-\frac{nE_{0}}{k_{B}T}}}
$$
<br>

$$
\LARGE
<E>\;=\frac{\sum_{n=0}^{\infty}\;nE_{0}e^{-\frac{nE_{0}}{k_{B}T}}}{e^{-\frac{}{}}\sum_{n=0}^{\infty}\;e^{-\frac{nE_{0}}{k_{B}T}}}
$$
<br>





