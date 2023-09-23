# The Hilbert space and Hamiltonian

## Fermions or bosons? From two particle systems

The most important difference between a classical and a quantum system is now the status of the system is described by a wave function. What qualitative new structure will be given by this difference? The wave function description will lead to a striking effect when we consider the many-particle systems since we loose the ability to distinguish identical particles by their "path".

Identical particles are the particles with identical intrinsic properties such as mass, charge, spin, *etc.*. For classical systems, we can always use the path to track individual particles in principle. However, this becomes impossible when the wave functions between two particles has overlap with each other. The difficulty came from the uncertainty of the positions of those particles.

Because of that, when the two wave function has measurable overlap, the probability description of the two particles should be indistinguishable, *i.e.* $P(\textbf{x}_1,\textbf{x}_2)=P(\textbf{x}_1,\textbf{x}_2)$. Because the probability of the quantum system is related to the norm square of the wave function. That automatically leads to the fact that the corresponding two particle wave function is equal up to a phase factor. *i.e.* $\phi(\textbf{x}_1,\textbf{x}_2)=e^{i\theta}\phi(\textbf{x}_2,\textbf{x}_1)$. Let's consider this effect as we swap the particle 1 and particle 2 of our original wave function. We immediately notice that swapping twice will return to the original wave function. That is, $(e^{i \theta})^2=1$. So we have $e^{i\theta}=\pm 1$. For bosons, we have $e^{i\theta}= +1$. For fermions, we have $e^{i\theta}= -1$. This is the starting point to discuss quantum statistics.

From the property that $\phi(\textbf{x}_1,\textbf{x}_2)=\pm\phi(\textbf{x}_2,\textbf{x}_1)$. We can divide the wave functions into two big categories. The symmetrized wave function, for bosons, and the anti-symmetrized wave function, for fermions.

$$
\phi^{B}(\textbf{x}_1,\textbf{x}_2)=\phi_a(\textbf{x}_1)\phi_b(\textbf{x}_2)+\phi_a(\textbf{x}_2)\phi_b(\textbf{x}_1)\\
\phi^{F}(\textbf{x}_1,\textbf{x}_2)=\phi_a(\textbf{x}_1)\phi_b(\textbf{x}_2)-\phi_a(\textbf{x}_2)\phi_b(\textbf{x}_1)\text{.}
$$
Here, $a,b$ are the quantum number of the system. For fermion, we can see if $a=b$, the wave function becomes zero. That is the Pauli exclusive principle applied to this simple setting.

For example, photon and phonon are bosons. Electron and neutron are fermions.

```{admonition} What?
:class: tip
It seems above argument is quite general. However, something sutble will happen in two-dimensional space. There, the swapping operation is not so trivial. Therefore, a different quantum statistical behavior other than fermion or boson is possible. Such a particle is called 'anyon'. One of the simplest model demonstrate anyon physics is the [toric code model](https://topocondmat.org/index.html). Anyons could be used in quantum computation and therefore has attract lots of attention recently. Some recent breakthrough on related subjects including {cite:p}`semeghini2021probing` and {cite:p}`satzinger2021realizing`.
```

## Quantum many-body system (non-interacting limit)

Now we know we have Fermions and Bosons. How to describe such a quantum system? To define a quantum system, we need to specify the Hamiltonian, $H$, and the corresponding Hilbert space,$\mathcal{H}$. Here, I will give a quick overview of the general description of quantum many-body systems with $N$ particles.

### The Hilbert space

Let's consider the wave function of distinguishable many-body system first. Since the particles are distinguishable, we can label the Hilbert space accordingly. The total Hilbert space is

$$
\mathcal{H}=\mathcal{H}_1\otimes\mathcal{H}_2\otimes\cdots\mathcal{H}_N
$$

The state in this Hilbert space can be represented by 

$$
\vert \psi\rangle=\vert\phi _{\gamma_1}\rangle_1\otimes\vert\phi _{\gamma_2}\rangle_2\otimes\cdots\vert\phi _{\gamma_N}\rangle_N\text{.}
$$

Here, $\vert\phi_{\gamma_i}\rangle_j$ is the complete set in $\mathcal{H}_j$ with quantum number $\gamma_i$.
Next, we can ask how a wave function is represented as ket vectors in our simple two particle example above.

$$
\phi^{B/F}(\textbf{x}_1,\textbf{x}_2)=\sqrt{2}^{-1}\left[\phi_{\gamma_1}(\textbf{x}_1)\phi_{\gamma_2}(\textbf{x}_2)\pm \phi_{\gamma_1}(\textbf{x}_2)\phi_{\gamma_2}(\textbf{x}_1)\right]=\langle \textbf{x}_1,\textbf{x}_2\vert \phi^{B/F}\rangle\\
\vert \phi^{B/F}\rangle = \frac{1}{\sqrt{2}}\left[\vert\phi_{\gamma_1}\rangle_1\otimes \vert\phi_{\gamma_2}\rangle_2\pm \vert\phi_{\gamma_1}\rangle_2\otimes \vert \phi_{\gamma_2}\rangle_1\right] \text{.}
$$

Comparing the simple two particle wave function and the wave function of distinguishable particles, we can get some hint about how should we proceed for a general $N$ particle system -- symmetric summation or anti-symmetric summation.

The generalization for $N$ particle system should be

$$
\vert \phi^B_N\rangle =\sqrt{N!}^{-1}P_{S}\left[ \vert \phi_{\gamma_1}\rangle_1 \otimes\vert \phi_{\gamma_2}\rangle_2 \otimes\cdots\otimes\vert \phi_{\gamma_N}\rangle_N\right]\\
\vert \phi^F_N\rangle =\sqrt{N!}^{-1}P_{AS}\left[ \vert \phi_{\gamma_1}\rangle_1 \otimes\vert \phi_{\gamma_2}\rangle_2 \otimes\cdots\otimes\vert \phi_{\gamma_N}\rangle_N\right]
$$
where

$$
P_{S/AS}\left[ \vert \phi_{\gamma_1}\rangle_1 \otimes\vert \phi_{\gamma_2}\rangle_2 \otimes\cdots\otimes\vert \phi_{\gamma_N}\rangle_N\right]=\sum_{p}\eta^{\overline{p}}\vert \phi_{\gamma_1}\rangle_{p(1)} \otimes\vert \phi_{\gamma_2}\rangle_{p(2)} \otimes\cdots\otimes\vert \phi_{\gamma_N}\rangle_{p(N)}\text{.}
$$

Here, $\eta=\pm1$ for symmetric or anti-symmetric summation, $p$ is an element of the $N$ object permutation. $p(j)$ is the $j$-th object of this permutation. $\overline{p}$ represent an integer which is the number required to swap nearby elements in the permutation $p$ such that it gets back to an ordered permutation. For example, for a 3 object permutation $p=[231]$, $\overline{p}=2$ since we need to swap 31 then swap 21 to get to the permutation $[123]$.  The summation contains $N!$ terms. That's why the normalization factor is $\sqrt{N!}^{-1}$.

From this construction, we can also see the Pauli exclusion principle. When $\gamma_i=\gamma_j$, the pairs of permutations related by a swap between $p(i)$ and $p(j)$ will differ by a minus sign. All such pairs therefore cancels with each other and leads to the Pauli exclusion principle.

We start from something simple and derive the generalized form for the many-body wave function when the indistinguishable nature of quantum particles are considered.

### The many-body Hamiltonian

$$
H=\sum_i H_i+\underbrace{\sum_{i,j} H_{i,j}+...}_{=0,\text{for non-interacting systems}}\text{.}
$$

When we diagonalize the many-body Hamiltonian, $H$, we will have the many-body eigen energy spectrum, $\left\{E_{\gamma}\right\}$ and the many-body eigen states, $\left\{\vert E_{\gamma}\rangle\right\}$.

What exactly do we mean by $\sum_i H_i$. The correct interpretation of $H_i$ is

$$
H_i=\textbf{1}_1\otimes\textbf{1}_2\otimes\cdots\textbf{1}_{i-1}\otimes H_i\otimes \textbf{1}_{i+1}\cdots \otimes\textbf{1}_N
$$
That is, the operator $H_i$ only acts non-trivially on the Hilbert space of the $i$-th particle.

Suppose the kets $\vert \phi_{\gamma'}\rangle_j$ are the eigenstates of the Hamiltonian $H_j$, *i.e.* $H_j|\phi_{\gamma'}\rangle_j=E_{\gamma'}|\phi_{\gamma'}\rangle_j$. The corresponding eigenstates with many-body energy $E_{\gamma}$ is $H\vert \phi ^{B/F}_N\rangle=\left(\sum_j E_{\gamma_j}\right) \vert \phi^{B/F}_N\rangle=E_{\gamma}\vert \phi^{B/F}_N\rangle$. The big difference of boson and fermion is the Pauli exclusion principle, we can have all the bosons sitting on the same state to lower the total energy; for fermions, they need to be stacked one by one. That corresponds to the two very important concepts, the Bose-Einstein condensation and the concept of fermi sea.

# Partition function for free fermions and bosons

In principle, the $\gamma_j$ in the above expression of the many-body wave function can be any quantum number. For example, for a free particle, $\gamma_j$ can be the index of momentum $p_j$. We can describe our system as the $j$-th particle has momentum $p_j$ then symmetrize/anti-symmetrize the whole wave function as we did currently. However, one can also use another representation to describe the state. That is, we know don't have the concept of $j$-th particle, maybe we can just count how many particles have a specific momentum $p_a$. Then, we can describe our system using those numbers $\{n_{p_1},n_{p_2},\cdots, n_{p_a},\cdots\}$. If we did so for our $N$ particle system, the representation must satisfy the constraint that $\sum_a n_{p_a}=N$. Here, we use $a$, which is the index for the quantum number (momentum in this case), as a distinct label with the index of the particle $j$.

Let's start from here to construct the canonical ensemble of quantum gases with internal degree of freedom $\alpha$ using the occupation number representation.

$$
Z_N=\sum_{\alpha}\sum_{\{n_{p_a,\alpha}\}} \delta_{\left(\sum_{\alpha}\sum_a n_{p_a,\alpha}\right),N} \exp\left[-\beta\left(\sum_{\alpha}\sum_{a}\frac{\textbf{p}_a^2}{2m}n_{p_a,\alpha}\right)\right]\text{.}
$$

This representation is nice, since we consider the indistinguishable nature of the quantum identical particles. No index for the label of particles anymore! However, we need to pay the price for the nontrivial constraint given by the Kronecker delta function. It is very tempting to relax the constraint by switching to the grand canonical ensemble where we introduce the chemical potential. We then have

$$
Z_{GC}=\sum_{N=0}^\infty Z_N e^{\beta \mu N}=\sum_{\alpha}\sum_{\{n_{\textbf{p}_a}\}} \exp\left[-\beta\left(\sum_{\alpha}\sum_{a}\left(\underbrace{\frac{\textbf{p}_a^2}{2m}}_{\epsilon(\textbf{p}_a,\alpha)}-\mu\right)n_{\textbf{p}_a,\alpha}\right)\right]\\
\xrightarrow{\text{factorizable}}\prod_{\alpha} \prod_{\textbf{p}_a} \underbrace{\left[\sum_{n_{\textbf{p}_a}} \exp\left(-\beta (\epsilon(\textbf{p}_a)-\mu) n_{\textbf{p}_a,\alpha}\right)\right]}_{\zeta(\epsilon(\textbf{p}_a,\alpha)-\mu)}\text{.}
$$
Here, we take advantage of the factorizable structure of a partition function for interacting free systems. Also, the specific form of the energy of the system is not important. We simply replace that by $\epsilon(\textbf{p}_a)$. 

For fermions, we have $n_{\textbf{p},\alpha}=0,1$

$$
\zeta(\epsilon(\textbf{p},\alpha)-\mu)=\zeta_F(\epsilon(\textbf{p},\alpha)-\mu)=1+\exp\left[-\beta(\epsilon(\textbf{p},\alpha)-\mu)\right]\text{.}
$$

For bosons, we have $n_{\textbf{p},\alpha}=0,1,\cdots, \infty$

$$
\zeta(\epsilon(\textbf{p},\alpha)-\mu)=\zeta_B(\epsilon(\textbf{p},\alpha)-\mu)=\frac{1}{1-\exp\left[-\beta(\epsilon(\textbf{p},\alpha)-\mu)\right]}\text{.}
$$

The two result could be summarized into

$$
\zeta(\epsilon(\textbf{p},\alpha)-\mu)=\zeta_{\eta}(\epsilon(\textbf{p},\alpha)-\mu)=\left(1-\eta\exp\left[-\beta(\epsilon(\textbf{p},\alpha)-\mu)\right]\right)^{-\eta}
$$
with  $\eta=+1/-1$ for bosons/fermions. If we try to think about what is the meaning of $\zeta_{\eta}$. We can realize that $\zeta_{\eta}(\epsilon(\textbf{p},\alpha)-\mu)$ is like the grand partition function for the mode $(\textbf{p},\alpha)$! So even though we are studying a many-particle system, once we relax the particle number constraint by going to the grand canonical ensemble, we can study the grand partition function for each mode as if they are independent!

From now on, we will use the $\zeta_{\eta}$ function to get the general expression of the grand canonical partition function and the corresponding thermodynamic potential for non-interacting fermions and bosons.

To move forward, we will try to derive the expression of $\ln Z_{GC}$. We immediately see

$$
-\frac{\Omega}{k_BT}=\ln Z_{GC}=
\sum_{\alpha}\sum_{\textbf{p}_a}\ln \zeta_{\eta}(\epsilon(\textbf{p}_a,\alpha)-\mu)\\
\xrightarrow{\text{trivial sum of } \alpha}
(2S+1)\sum_{\textbf{p}_a}\ln \zeta_{\eta}(\epsilon(\textbf{p}_a)-\mu)=(2S+1)\sum_{\textbf{p}_a}\left(-\frac{\Omega_{\textbf{p}_a}}{k_BT}\right)
\text{.}
$$

In the last line, if we assume the energy $\epsilon(\textbf{p}_a,\alpha)$ is independent of the internal degree of freedome $\alpha$ (such as spin), we expect the summation over $\alpha$ only provides a trivial factor. In the simple cases such as interacting free fermi/bose gases, we expect this relation to hold. Therefore, $\sum_{\alpha}\to (2S+1)$. Here, we assume we are discussing particles that are not gauge particles, so the internal degrees of freedom is related to the spin value $S$. ( *e.g.* Spin $1/2$ has two possible internal states, spin up or spin down. It turns out, there is a **spin-statistics theorem** for Lorentz invariant systems. We will leave the readers to check the quantum field theory textbooks. {cite:p}`srednicki1994chaos` )

Once we take the log, the product over $\textbf{p}_a$ turns into a summation. So we can ask the question. What is the expectation value of particles sitting at the particular momentum $\textbf{p}_a$? We can again see the influence of the interacting free assumption and the advantage of using grand canonical ensemble, the modes are basically decoupled! So when we ask the average value of the occupation number, we can simply evaluate it using $\langle n_{\textbf{p}_a}\rangle= -\frac{\partial \Omega_{\textbf{p}_a}}{\partial \mu}$. That is,

$$
\langle n_{\textbf{p}_a}\rangle= -\frac{\partial \Omega_{\textbf{p}_a}}{\partial \mu}=-\frac{\partial}{\partial \mu} (-\eta)(-\beta)^{-1}\ln(1-\eta e^{\beta(\mu-\epsilon(\textbf{p}_a))})=\frac{e^{\beta(\mu-\epsilon(\textbf{p}_a))}}{1-\eta e^{\beta(\mu-\epsilon(\textbf{p}_a))}}=\frac{1}{e^{\beta(\epsilon(\textbf{p}_a)-\mu)}-\eta}\text{.}
$$

This is the average number of fermions/bosons to occupy a state $\textbf{p}_a$. The corresponding function form is called the Fermi-Dirac/ Bose-Einstein distribution function. In the process to derive this expression, we did not use any properties related to the energy is quadratic in momentum. The expression actually holds for all possible quantum sates as long as the system described by the quantum number is non-interacting. Therefore, we should have a more general expression

$$
\langle n_{\gamma}\rangle=\frac{1}{e^{\beta(\epsilon(\gamma)-\mu)}-\eta}
$$
for a single particle state $\gamma$. This is the famous Fermi-Dirac distribution function($\eta=-1$) or the Bose-Einstein distribution function($\eta=+1$).

Let's try to see what happened if we put back the quadratic momentum dependence in the $\epsilon(\textbf{p})=\frac{\textbf{p}^2}{2m}$ and the fugacity $z=e^{\beta \mu}$.

We will have

$$
\ln Z_{GC}=(2S+1)\left(\frac{L}{h}\right)^3\int d^3{\textbf{p}} (-\eta) \ln\left[1-\eta z e^{-\frac{\textbf{p}^2}{2mk_BT}}\right]\\
=(2S+1)\left(\frac{L}{h}\right)^3(4\pi)\int_0^{\infty}p^2dp (-\eta) \ln\left[1-\eta z e^{-\frac{\textbf{p}^2}{2mk_BT}}\right]\\
\xrightarrow{p=\sqrt{2mk_BT}\tilde{p}}(2S+1)\left(\frac{L}{h}\right)^3(4\pi)\sqrt{2mk_BT}^3 (-\eta) \int_0^{\infty}\tilde{p}^2d\tilde{p}\ln\left[1-\eta z e^{-\tilde{p}^2}\right]
$$

Using the relation $\ln(1+x)=-\sum_{n=1}^{\infty} \frac{(-x)^n}{n}$, we have

$$
\ln Z_{GC}=(2S+1)(4\pi) L^3\sqrt{\frac{2mk_BT}{h^2}}^3 (\eta) \left[\sum_{n=1}^{\infty}\frac{(\eta z)^n }{n}\int_0^{\infty}\tilde{p}^2e^{-n\tilde{p}^2}d\tilde{p}\right]\\
$$

We can notice the integral over $\tilde{p}$ is a Gaussian integral that we can derive exactly. This is the additional information from the quadratic momentum dependency of $\epsilon(\textbf{p})$.

$$	
\int_{0}^{\infty} q^2 e^{-nq^2}dq=\frac{1}{2}\left[ -\frac{\partial}{\partial n}\int_{-\infty}^{\infty}e^{-nq^2}dq \right]=\frac{1}{2}\left[ -\frac{\partial}{\partial n} \sqrt{\frac{\pi}{n}}\right]=\frac{1}{2}\frac{1}{2}\sqrt{\pi}n^{-\frac{3}{2}}\text{.}
$$

Using above result, spin-statistics theorem ($\eta\to(-1)^{2S}$) and the definition of polylog function $\phi_{\alpha}(z)=\sum_{n=1}^{\infty}\frac{z^n}{n^{\alpha}}$, we have

$$
\ln Z_{GC}=\eta (2S+1) \left(\frac{L}{\lambda}\right)^3 \phi_{\frac{5}{2}}(\eta z)
=(-1)^{2S} (2S+1) \left(\frac{L}{\lambda}\right)^3 \phi_{\frac{5}{2}}((-1)^{2S} z)\text{.}
$$

The expectation value of the total particle number is

$$
\langle \hat{N}\rangle=N= z\frac{\partial }{\partial z}\ln Z_{GC}= \eta (2S+1) \left(\frac{L}{\lambda}\right)^3 \phi_{\frac{3}{2}}(\eta z)\text{.}
$$

Here we use the relation $z\frac{\partial}{\partial z} \phi_{\alpha}(cz)=\phi_{\alpha-1}(cz)$.

## Classical limit of the quantum gases

When $z\ll 1$, we can approximate $\phi_{\alpha}(\eta z)\sim \eta z$. In that limit, we can solve $z$ as a function of $N$. We have

$$
z\approx \frac{1}{2S+1}\frac{N\lambda^3}{L^3}\equiv \frac{1}{2S+1} \xi\text{.}
$$

Here $\xi=\frac{\lambda^3}{L^3/N}$ is dimensionless parameter which is the ratio between the de Broglie's thermal volume and the average volume occupied by a particle. 

Here is a self-consistency check, we assume $z\ll1$ to simplify the relation of $N$ and $z$. This leads to an expression of $z$ as a function of $\xi$. In this limit, we can also see that $\ln Z_{GC}\approx N=\frac{pV}{k_BT}$ is the classical equation of state. And we know at the classical limit corresponds to the $\xi\ll1$ limit. So $z$ which is proportional with $\xi$ is indeed a small quantity. So we finish the loop of internal consistency.

This derivation suggest that we can use $\xi$ to tell whether we are in the *quantum degenerate* region which means we need to consider the quantum statistics of our system. If $\xi\ll1$, we expect the quantum statistics can be neglected and we reach the classical limit. When $\xi\sim \mathcal{O}(1)$, we consider the system to be quantum degenerate.

## Degenerate Fermi gases

Now let's think about the quantum limit and if the system is formed by fermions. As we have discussed, the Pauli exclusion principle will play an important role for the statistical behavior of the system. Let's take the Fermi-Dirac distribution function and think about the meaning of this result. When $\eta=-1$, we have

$$
n_{F}(\epsilon)=\frac{1}{e^{\beta[\epsilon-\mu]}+1}<1\text{.}
$$

Here $\epsilon$ is the single particle energy of the occupied state.
The first thing we should notice is the distribution function is always smaller than 1! That reflects the Pauli exclusion principle. At the low temperature limit, we have $\beta\to\infty$.The sign of $\epsilon-\mu$ will change the value of $n_{F}$ significantly. When $\epsilon>\mu$, $n_{F}\to0$; when $\epsilon<\mu$, $n_{F}\to1$. At $T=0$ the threshold $\mu(T=0)$ is the Fermi energy, $E_F$, which represent the maximum energy of the occupied states. For arbitrary temperature, we have

$$
N=V\int_0^{\infty} dE g(E)n_F(E) \text{.}
$$
Here, $g(E)$ is the density of states per volume at energy $E$.
We can calculate the fermi energy for given particle number $N$ easily by sending $T\to0$. At this limit, we have

$$
N=V\int_0^{\mu(T=0)=E_F} dE g(E) 
$$
since $n_F(E)$ becomes a step function. The density of states will depends on the Hamiltonian of the system. Once we have that information, we can express the fermi energy as a function of particle number $N$.

One important behavior of the Fermi-Dirac distribution function is the linear temperature dependence of the low energy specific heat. This behavior is quite general and can be considered via the following argument.

The specific heat is related to the change of energy $\Delta E$ when the temperature is changed. Because most of the states at low energy is occupied, therefore, they will not contribute to the change of energy as we smoothly varying the temperature. Therefore, we only care about the states near the fermi energy. At temperature $T$ only states within the energy window $\Delta E\approx k_BT$ will be the active states. The number of such state is $D(E_F)\Delta E= D(E_F)k_BT$. Since the particle number is fixed, the thermal fluctuation will just drive the fermions from some lower energy state to a higher energy state. The change of energy is of the scale $k_BT$. For a system with $E_F\gg k_BT$, the energy change can be approximated as $\delta E=(D(E_F)k_B \delta T)(k_BT)$. Therefore, we expect $C=\frac{\delta E}{\delta T}\propto T$. Therefore, if we observe low temperature specific heat has a linear temperature dependence. It is suggesting the low energy carrier might be fermions forming a fermi sea. And the states near the fermi surface contribute to the energy transport.

To have a more detailed calculation of electrons in metal. We can apply the [Sommerfeld expansion](https://en.wikipedia.org/wiki/Sommerfeld_expansion) to the Fermi-Dirac distribution. I will leave it as an exercise for the readers.

## Degenerated Bose gases 

Let's focuse on the $\eta=+1$ case for bosons.

$$
n_{B}(\epsilon)=\frac{1}{e^{\beta[\epsilon-\mu]}-1}\text{.}
$$

This expression came form the geometric series with ratio $e^{-\beta(\epsilon-\mu)}<1$. Suppose we choose the energy minimum of the system to be the zero point of energy. Then we have the condition that the fugacity $z=e^{\beta\mu}<1$ which implies $\mu<0$.

The total particle number of the system in $D$ spatial dimension can be expressed as 

$$
N=(2S+1)\sum_{\textbf{p}_a} n_B(\textbf{p}_a)=(2S+1)\left(\frac{L}{h}\right)^D \int_0^{\infty} S_Dp^{D-1}dp\frac{1}{e^{\frac{p^2}{2mk_BT}}z^{-1}-1}\\
\xrightarrow{p\to\sqrt{2mk_BT} x}
(2S+1)L^D\left(\sqrt{\frac{2\pi mk_BT}{h^2}}\right)^D\frac{2}{\Gamma(D/2)}\underbrace{\int_0^{\infty}ze^{-x^2}\frac{1}{1-ze^{-x^2}} x^{D-1}dx}_{\text{monotonic increasing function of }z}\\
=(2S+1)\left(\frac{L}{\lambda}\right)^D\frac{2}{\Gamma(D/2)}\sum_{n=1}^{\infty} z^n \underbrace{\int_0^{\infty}x^{D-1} e^{-nx^2}dx}_{\Gamma(D/2)/(2n^{D/2})}\\
=(2S+1)\left(\frac{L}{\lambda}\right)^D\phi_{D/2}(z)<(2S+1)\left(\frac{L}{\lambda}\right)^D\phi_{D/2}(z=1)
$$

Here, $D=2$ corresponds to the Riemann zeta function $\zeta_R(1)\to\infty$. When $D=3$, we have $\zeta_R(3/2)\approx 2.6...$. When $\phi_{D/2}(1)=C_D$ is finite, we got an inequality that the total particle number must satisfied. 

$$
N<(2S+1)C_D\left(\frac{L}{\lambda}\right)^{D}
$$

However, as we know $\lambda\propto T^{-1/2}$. As $T\to0$, $\lambda\to\infty$. At the temperature $T_c$ this inequality will be violated. How is it possible? What went wrong in our derivation?
It turns out the argument above fails when $n_B(\epsilon)$ have singular behavior. When we are at $\textbf{p}=0$, we have

$$
n_B(0)=\frac{1}{z^{-1}-1}\text{.}
$$

When we send $z\to1$ to get the upper bound of $N$, the occupation number at $\textbf{p}=0$ diverges. That is, the replacement of the discrete summation and the integral needs to be interpreted more carefully.

Once we observe this behavior, we know we should separate the $\textbf{p}=0$ mode with the rest $\textbf{p}\neq0$ modes. The $\textbf{p}\neq0$ modes can be approximated by the integral expression without problem. Therefore, we can calculate the particles occupying the $\textbf{p}=0$ mode by

$$
N_{\textbf{p}=0}=N-N_{\textbf{p}\neq0}=N-(2S+1)\left(\frac{L}{\lambda}\right)^D\phi_{D/2}(z)>N-(2S+1)\left(\frac{L}{\lambda}\right)^D\phi_{D/2}(1)\\
=N\left[1-\underbrace{(2S+1)\frac{1}{N}\left(\frac{L\sqrt{2\pi m k_B}}{h}\right)^D\phi_{D/2}(1)}_{T_c^{-D/2}} T^{D/2}\right]=N\left[1-\left(\frac{T}{T_c}\right)^{D/2}\right]
$$

On the other hand, the fugacity $z$ is determined by the number of particles at $\textbf{p}\neq0$. That is,

$$
N_{\textbf{p}\neq0}=(2S+1)\left(\frac{L}{\lambda}\right)^D\phi_{D/2}(z)<(2S+1)\left(\frac{L}{\lambda}\right)^D\phi_{D/2}(1)\equiv N_{\textbf{p}\neq0}^M\text{.}
$$

When $N<N_{\textbf{p}\neq0}^M$, everything is fine, since we can always find states with $\textbf{p}\neq0$ to put our bosons and adjust $z$ accordingly. If we keep adding more bosons to the system at the same temperature then $z$ starts to increase and approaches 1. At some critical value of particle number, we can no longer put states at $\textbf{p}\neq0$ since they are "filled". The only place to put the boson is to put them at $\textbf{p}=0$.
From the Bose-Einstein distribution, we have $N_0=\frac{1}{z^-1-1}$. We can find $z=\frac{N_0}{N_0+1}$. When the boson is put at $\textbf{p}=0$, $N_0$ increases and $z$ gets closer to 1. When $N_0$ is large, we can see $z$ approaches 1 as $z\approx 1-N_0^{-1}$.


