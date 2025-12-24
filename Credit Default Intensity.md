
# Default and Survival Probability

**Default probability:** $P(\tau \leq t)$.

**Survival probability:** $P(\tau > t) = Q(t)$.

**Conditional default probability:** $P(\tau \leq t + dt \mid \tau > t)$.

**Conditional survival probability:** $P(\tau > t + dt \mid \tau > t)$.

***
 **Conditional survival probability**

$$P(\tau > t + dt \mid \tau > t) = \frac{P(\tau > t + dt \text{ AND } \tau > t)}{P(\tau > t)} = \frac{P(\tau > t + dt)}{P(\tau > t)} = \frac{Q(t + dt)}{Q(t)}.$$

**Conditional default probability**

$$P(\tau \leq t + dt \mid \tau > t) = 1 - P(\tau > t + dt \mid \tau > t) = \frac{P(\tau > t) - P(\tau > t + dt)}{P(t > \tau)} = \frac{P(\tau \leq t + dt) - P(\tau \leq t)}{P(t > \tau)}$$

$$= \frac{P(t < \tau \leq t + dt)}{P(t > \tau)}.$$

(or, by conditional probability formula directly)

$$P(\tau \leq t + dt \mid \tau > t) = \frac{P(t < \tau \leq t + dt)}{P(t > \tau)} = \frac{P(\tau \leq t + dt) - P(\tau \leq t)}{P(t > \tau)} = \frac{(1 - P(\tau > t + dt)) - (1 - P(\tau > t))}{P(t > \tau)}$$

$$= \frac{Q(t) - Q(t + dt)}{Q(t)} = -\frac{dQ(t)}{Q(t)}.$$

---

# Hazard Rate

**def.**

$$\lambda(t) = \frac{P(\tau \leq t + dt \mid \tau > t)}{dt}.$$

**Derivation:**

$$\lambda(t) = \frac{P(\tau \leq t + dt \mid \tau > t)}{dt} = \frac{P(\tau \leq t + dt) - P(\tau \leq t)}{P(t > \tau)} \cdot \frac{1}{dt} = \frac{1}{P(t > \tau)} \cdot \frac{P(\tau > t) - P(\tau > t + dt)}{dt}$$

$$= -\frac{d}{dt}\log P(\tau > t).$$

$$= -\frac{1}{P(t > \tau)} \cdot \frac{d}{dt}P(\tau > t).$$

Solve the ODE: $-\lambda(t)P(t > \tau) = \frac{d}{dt}P(\tau > t)$ with initial condition: $P(\tau > 0) = 1$.

**Solution: unconditional survival probability**

$$Q(t) = P(\tau > t) = \exp\left(-\int_0^t \lambda(u) du\right), t \geq 0$$


## Constant failure rate $\lambda(t) = \lambda > 0$

- $Q(t) = P(\tau > t) = \exp(-\lambda t)$ by the above solution
- $P(\tau \leq t) = 1 - \exp(-\lambda t)$.

So: $\tau \sim \text{Exp}(\lambda)$.

- Memoryless of exponential distribution: $P(\tau > t + dt \mid \tau > t) = P(\tau > dt) = \exp(-\lambda * dt)$.
- $P(t < \tau \leq t + dt) = \exp(-\lambda t) - \exp(-\lambda(t + dt))$.
- $P(\tau \leq t + dt \mid \tau > t) = 1 - \exp(-\lambda * dt)$.

Note that given $(\tau_n)_{n \geq 1}$ a sequence of i.i.d. exponentially distributed random variables, letting...  
$T_n = \tau_1 + \tau_2 + \cdots \tau_n, n \geq 1$,  
defines the sequence of jump times of a standard Poisson process with intensity $\lambda > 0$.

---

# Discrete Settings

Assume hazard rate is constant in an interval.

---

# From CDS curve to Default Probabilities
