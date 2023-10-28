# Ornstein-Ulhenbeck-process

Exercise 1 : 
The equation given is -

$$ \frac{dx(t)}{dt} = -\lambda x(t) + w(t); \:  x(0) = x_{0} $$

Rearranging the above equation yields a form that is familiar, 

$$ \frac{dx(t)}{dt}+\lambda x(t) =  w(t) \hspace{35pt}  (1) $$  

Motivated by the fact that ODE of this type can be usually solved using a specific method called integrating factor method which finds a factor that multiplies both sides to give an exaction differential equation, I try to apply this method to the given SDE above. The use of this method is justified because the ito's product rule allows it. 

$$ d(uv) = udv + vdu + dudv \hspace{35pt}  (2) $$

The cross term will vanish because covariance of deterministic function and a stochastic term will be zero.
Multiplying the integrating factor I.F = $e^{\int_0^t \lambda ds } $ on both sides of the equation (1), we get 

$$e^{\lambda t} \left(\frac{dx(t)}{dt}+\lambda x(t)\right) =  e^{\lambda t}w(t))$$
$$\implies \ e^{\lambda t} \frac{dx(t)}{dt} + e^{\lambda t} \lambda x(t) =  e^{\lambda t}w(t))$$
$$\implies \frac{d}{dt}(e^{\lambda t}x(t)) = e^{\lambda t}w(t)$$
$$\implies d(e^{\lambda t}x(t)) = e^{\lambda t}w(t)dt $$
$$\implies \int_0^t d(e^{\lambda t}x(t)) = \int_0^t e^{\lambda s}w(s)ds $$
$$\implies e^{\lambda t}x(t) - e^{\lambda (0)}x(0) = \int_0^t e^{\lambda s}w(s)ds $$
$$\implies x(t) - e^{-\lambda t}x(0) = e^{-\lambda t}\int_0^t e^{\lambda s}w(s)ds $$
$$\implies x(t) = x_{0}e^{-\lambda t} + \int_0^t e^{-\lambda (s-t)}w(s)ds $$
$$\implies x_{t} = x_{0}e^{-\lambda t} + \int_0^t e^{-\lambda (s-t)}w(s)ds $$

Mean:

$ m(t) = E[x_{t}] = E[x_{0}e^{-\lambda t} + \int_0^t e^{-\lambda (s-t)}w(s)ds]$

The expectation of deterministic function w.r.t brownian is zero. So the second term vanishes and we are left with the following expression for expectation, 

$ m(t) = x_{0}e^{-\lambda t} $

$\lim_{t \to \infty} m(t) = 0 $

Variance:

$ p(t) = E[(x_{t}-m(t))^2] = E[(\int_0^t e^{-\lambda (s-t)}w(s)ds)^2]$

Now using ito's isometry property we get,

$E[(\int_0^t e^{-\lambda (s-t)}w(s)ds)^2] = E[\int_0^t e^{-2\lambda (s-t)}ds] =  \frac{1}{2\lambda}(1 - e^{-2\lambda t})$

$p(t) = \frac{1}{2\lambda} (1 - e^{-2\lambda t})$

$\lim_{t \to \infty} p(t) = \frac{1}{2\lambda} $
