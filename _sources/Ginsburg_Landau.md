# The Ginsburg Landau theory

We will introduce the Ginsburg Landau theory which is a theory that describes the definition of phases and the transitions between them. The theory heavily relies on the principle of symmetry which will become more clear as we introduce the postulates and the structure of the theory. Before everything, let's understand what is the problem and what kind of tools we have at hands.

## Motivation -- Phases and phase transitions

Phases characterizes the pattern of collective behavior of a many-body system. When the pattern changes, we have a phase transition. In the equilibrium statistical mechanics, we learned that phases and phase transitions could be understood by the partition function. The key to have a well-defined notion of phase transition is to study the question at the thermodynamic limit where we could have non-analytic behavior from the combination of infinite many analytic functions.

The partition function for a system can be formally expressed as

$$
Z(N,\beta)=\sum_{c\in \mathcal{C}} e^{-\beta E(c)}\text{.}
$$
Here, $N$ is the number of degrees of freedom, $\beta=(k_B T)^{-1}$, $c$ represent an arbitrary configuration of the system in the configuration space $\mathcal{C}$ and $E(c)$ is the energy of the corresponding configuration $c$.

With the partition function defined, the probability of the configuration $c$ can be expressed as

$$
P(c)=\frac{1}{Z}e^{-\beta E(c)}; \sum_{c\in\mathcal{C}} P(c)=1\text{(The normalization condition).}
$$

The partition function is related to the free energy by a simple change of variable.

$$
Z(N,\beta)&=\sum_{c\in \mathcal{C}} e^{-\beta E(c)}=\sum_{E}\sum_{c\in \mathcal{C}}\delta_{E,E(c)} e^{-\beta E(c)}\\
&=\sum_{E} \underbrace{w(E)}_{\text{number of configurations at the specific energy } E} e^{-\beta E(c)}\\
&=\sum_E e^{-\beta E+\ln[w(E)]}=e^{-\beta F(N,\beta)}\text{.}
$$

The competition between energetics and the entropy can be observed clearly by taking derivative with respect to $\beta$ to the normalization condition above.

$$
\sum_{c\in\mathcal{C}} e^{\beta[F(N,\beta)-E(c)]}\left\{ \left[F(N,\beta)-E(c)\right]+\beta\left(\frac{\partial F}{\partial \beta}\right)_N\right\}=0
$$

The above equality leads to

$$
F(N,\beta)=\sum_{c\in\mathcal{C}}P(c)E(c)-\beta\sum_{c\in\mathcal{C}}P(c)\left(\frac{\partial F}{\partial \beta}\right)_N=\langle H\rangle -T \langle \left(-\partial_T F\right)_N\rangle\text{.}
$$

Adjusting temperature changes the weighting of $\langle H\rangle$ and $T \langle \left(-\partial_T F\right)_N\rangle$.  At low temperature limit, the first term dominates. At the high temperature limit, the latter dominates.

## Mean-field theory for Ising model

To have a more specific picture about the above abstract idea. Let's take the simplest non-trivial model for the study of phases-- the ferromagnetic Ising model.

The model is defined by interacting binary variables $\sigma_i=\{+1,-1\}$ on lattice site $i$. The Hamiltonian for the system $\Omega$ is

$$
H_{\Omega}=-J\sum_{\langle i,j\rangle} \sigma_i\sigma_j, J>0\text{.}
$$

Here, the binary variables prefer to have the same sign as dictated by the energy scale $J$. 

The system has the global Ising symmetry, $\sigma_i\to-\sigma_i$, which keep the Hamiltonian invariant. There are other symmetries such as the lattice symmetry which we will see does not play an important role for the discussion of the phase transition.

The probability of a spin configuration $P(c=\{\sigma_1,\sigma_2,\cdots,\sigma_N\})$ factorizes under the mean-field theory assumption. *i.e.* $P(c=\{\sigma_1,\sigma_2,\cdots,\sigma_N\})\xrightarrow{MFT} \prod_{i=1}^N P_{MFT}(\sigma_i)$. The corresponding probability $P_{MFT}(\sigma_i)$ is then determined in a self-consistent fashion.

The formal procedure is to replace the spin spin coupling using the expectation value that is determined by $P_{MFT}(\sigma_i)$. The replacement is valid when we assume the fluctuation $\delta \sigma \equiv \sigma_i-\langle \sigma_i\rangle_{MFT}$ is small and we only include terms up to $\mathcal{O}(\delta \sigma)$. The replacement

$$
\sigma_i\sigma_j\to \langle \sigma_i \rangle_{MFT} \sigma_j+\sigma_i\langle \sigma_j\rangle_{MFT}-\langle \sigma_i\rangle_{MFT}\langle \sigma_j\rangle_{MFT}
$$

effectively reduce the problem into a single particle problem with an effective magnetic field, $h_{eff,i}=\sum_{j\neq i} J_{ij}\langle \sigma_j\rangle_{MFT}$, applied on a single spin. For those who are not familiar with the mean-field theory approach, please check the lecture note of statistical mechanics (I).

We can stand back and ask what is the key assumption in the mean-field theory? It turns out the assumption that $\delta \sigma\approx0$ is the key for the mean-field theory to work. If the statement is true, then we can drop the fluctuation. This situation happened when the system is deep in a specific phase. On the other hand, when the system is near the transition, the fluctuation is not small, then the approach will be problematic. We will revisit this issue later. For now, let's pretend the mean-field theory is valid for all temperature range and move on to do the corresponding calculation.

The key equation for us to solve is the self-consistency equation. At this step, I will put back the coupling with the external magnetic field, $h$, to remind ourselves about how to use the mean-field theory to calculate the critical exponents. The self-consistency equation is

$$
\langle \sigma_i\rangle_{MFT}=m=\tanh\left[ \beta (h+m k_B T_c)\right]; T_c=\frac{2dJ}{k_B}\text{.}
$$

Once $m$ is determined, we can construct the effective magnetic field and recover $P_{MFT}(\sigma_i)$. With these information, we can calculate the critical exponents by expanding the self-consistency equation near the critical temperature.

## Concept of order parameter

One can immediate notice that $\langle \sigma_i\rangle_{MFT}$ plays an important role in the above approach. It is actually the parameter that specifies the corresponding order. When $\langle \sigma_i\rangle_{MFT}\neq0$, it specifies the system is ordered. However, the quantity is defined within the mean-field theory. Why not promoting this idea to a more general setting beyond the mean-field theory. After all, the mean-field theory is just a theory for us to approximate the $P(\{\sigma_1,\sigma_2,\cdots,\sigma_N\})$.

We can take the idea and define an observable $\mathcal{O}$. When $\langle \mathcal{O}\rangle \neq0$, the probability distribution develop some kind of collective pattern that is specified by $\langle \mathcal{O}\rangle$, so we call it the *order parameter*. The order parameter can be a scalar, a vector, a tensor or even a function. We will focus on the simple case for now. For the Ising model, it is just the magnitude of $m$.

## The "Landau free energy"

### A little bit of reverse engineering...

Now we know the idea of the mean-field theory and the order parameter. For different problems, we will need to run the same machinery again and again. Can we find the common features between those mean-field theories? The key equation seems to be the self-consistency equation. Can we make some physical arguments and directly get the essential information of the self-consistency equation?

Let's first define what do we mean by the essential information. In the study of critical phenomena, we basically look for the so-called critical exponents. When the temperature is near the critical temperature, the order parameter will be small and we might expand the self-consistency equation and solve them approximately. In the case of Ising model, we essentially can do the analysis by sending $T\to T_c$ and $m\approx0$ at small external field $h$. The self-consistency equation becomes

$$
\frac{h}{k_B T}\approx (1-\tau)m+\left[\tau-\tau^2+\frac{\tau^3}{3}\right]m^3+\cdots\\
\text{or equivalently}\\
(1-\tau)m+\left[\tau-\tau^2+\frac{\tau^3}{3}\right]m^3-\frac{h}{k_B T}\approx
$$ (critical-equation)

here, $\tau=\frac{T_c}{T}$ and we can get all the critical exponents starting from this equation.

So the question is: can we define some kind of concept that is similar to the free energy in thermodynamics and minimize it to get the above self-consistency equation near the critical temperature? If we can do that, that concept will be useful. Then we can go back and ask how to justify this seemly *ad hoc* free energy on a physical ground.

Let's just try to do the exercise for our Ising model problem with equation [](critical-equation). If we define some kind of "free energy" $\Gamma(T,J,h,m)$. We can always devide it into parts that are independent of $m$ completely and parts that depends on $m$ implicitly. We would like to have the part that has implcit dependence on $m$ provides the minimization equation which is equivalent to [](critical-equation). The following construction will work.

$$
\Gamma(T,J,h,m)\equiv \Gamma_0(T,J,h)+\underbrace{U[\Gamma_0(T,J,h)]}_{\text{To make sure the expression has the right unit.}}\int dm K(T,J,h,m)\text{.}
$$

The minimization condition is

$$
\frac{\partial \Gamma}{\partial m}=0=(1-\tau)m+\left[\tau-\tau^2+\frac{\tau^3}{3}\right]m^3-\frac{h}{k_B T}\text{.}
$$

So we can see the idea is very tempting! It is indeed possible at least formally. If we perform the last integral, we can see

$$
\Gamma(T,J,h,m)\equiv \Gamma_0(T,J,h)+U[\Gamma_0(T,J,h)]\left\{(1-\tau)\frac{m^2}{2}+\left[\tau-\tau^2+\frac{\tau^3}{3}\right]\frac{m^4}{4}-\frac{h}{k_BT}m\right\}\text{.}
$$

All the important information is hidden in the last term. The question is: can we have a theoretical argument to construct it directly? It turns out, it is the Landau theory.

### The postulates

Here we discuss the postulates for the Landau theory. The key step toward the physical argument of the Landau theory is to identify the transformation property of the order parameter under the symmetry of the system. We will discuss the postulates first and apply it to the Ising model and see what we can learn during the procedure.

1. We can construct the Landau free energy, $L$, as
   
   $$
   L\left[\left\{K_i\right\},\eta\right]
   $$
   with the order parameter $\eta$ and couplings $\{K_i\}$.
2. How to construct $L$? 
   1. $\eta$ transforms under the symmetry of the system.
   2. $L$ is invariant under the symmetry transformation.
   
   Taking the Ising model as an example, the order parameter $\eta=\langle \sigma_i\rangle\xrightarrow{\text{Ising symmetry}}-\eta$. As the temperature is below the critical temperature, $\eta\neq0$. The symmetry is spontaneously broken. When the temperature is above the critical temperature $\eta=0$ the symmetry is preserved.
3. $L$ is analytic in $\eta$ around $\eta=0$. We will see that it is convenient to discuss the density of $L$ defined as
   
   $$
   \mathcal{L}=\frac{L}{V}=\sum_{p=0}^{\infty}a_p(\{K_i\})\eta^p\text{ when } \eta\approx0\text{.}
   $$
4. For inhomogeneous system, we require $\mathcal{L}$ to be a local function of $\eta(\textbf{r})$ and $\nabla^q \eta(\textbf{r})$ with $q$ finite.
5. When $T>T_c$, the solution of the minimization equation of $\mathcal{L}$ is $\eta=0$. When $T<T_c$, the solution is $\eta\neq0$.


### Phenomenological Landau theory for the Ising model

Let's try to construct the phenomenological Landau theory for the Ising model. 

$$
H=-J\sum_{\langle i,j\rangle}S_iS_j; J>0\text{.}
$$

The important object is the order parameter. In this case, the symmetry of the Hamiltonian is the Ising symmetry $S_i\to-S_i$. The simplest observable that breaks the symmetry is $\langle S_i\rangle\equiv \eta$. We will use it to be the order parameter and construct the corresponding Landau free energy. 

#### Constructing the Landau free energy

We start our process by considering the homogeneous case where $\eta(\textbf{r})=\eta$ and $\nabla \eta(\textbf{r})=0$. From the postulate 3 we know

$$
\mathcal{L}=a_0(J,T)+a_1(J,T)\eta+a_2(J,T)\eta^2+a_3(J,T)\eta^3+a_4(J,T)\eta^4+\cdots
$$

From postulate 2, the Ising symmetry requires $\mathcal{L}(\eta)=\mathcal{L}(-\eta)$. Therefore, we only keep the even power terms.

$$
\mathcal{L}=a_0(J,T)+a_2(J,T)\eta^2+a_4(J,T)\eta^4+\cdots
$$
To avoid the cluttering notation, we will supress the $(J,T)$ dependence. But we should keep in mind that those coeficients all depends on $J$ and $T$ implicitly.

We will use postulate 5 to determine the behavior of the phenomenological constants across the critical temperature $T_c$. We first notice the minimization condition of the Landau free energy has two solutions

$$
\frac{\partial \mathcal{L}}{\partial \eta}=2a_2\eta+4a_4\eta^3=0
$$

with two solutions

$$
\eta=
\left\{
\begin{array}{c}
0\\
\pm \sqrt{-\frac{a_2}{2a_4}}\equiv \pm \eta_{SB}
\end{array}
\right.
\text{.}
$$

Our goal is to have $\eta=0$ to be the stable solution for the Landau free energy when $T>T_c$ and $\eta=\pm\eta_{SB}$ when $T<T_c$. How to achieve our goal? We can make the following observation, the functional form of the Landau free energy is essentially a quadratic equation in disguise. That is, we can rewrite the free energy in the form of $A_1(\eta^2+A_2)^2$. To have a well defined minimum, we need to have $A_1>0$. If $A_2>0$, the free energy is minimized when $\eta^2=\eta=0$. If $A_2<0$, the free energy is minimized when $\eta^2=-A_2>0$. Therefore, we can reverse engineer the properties we want. That is, we require $a_4(J,T)>0$ and $a_2(J,T)$ to change sign accordingly at $T=T_c$! With these information, we could find the leading order behavior of $a_0(J,T),a_2(J,T)$ and $a_4(J,T)$ in temperature.

$$
a_0(J,T)\simeq a_0(J)+\cdots\\
a_2(J,T)\simeq a\left(\frac{T-T_c}{T_c}\right)\cdots\\
a_4(J,T)\simeq a_4(J)+\cdots\text{.}
$$

#### The critical exponents

#### Effects of external fields

## The microscopic meaning of the "Landau free energy"

## The functional integral representation of Landau theory

microscopic meaning of each parameter
