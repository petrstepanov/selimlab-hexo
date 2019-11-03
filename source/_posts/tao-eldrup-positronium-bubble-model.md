---
title: Tao-Eldrup positronium bubble model
date: 2017-04-19 00:49:58
tags:
mathjax: true
---

Tao-Eldrup model provides a simple but widely used correlation between the ortho-positronium bubble size and its lifetime in solid media.
<!--more-->
The ortho-positronium (o-Ps) lifetime in vacuum is approximately 142ns whereas in solid media it is considerably less approximately 10-100 times. The phenomena is described by so-called pick-off annihilation process when an electron form positronium atom is annihilated by another nearby electron.

The first person who attempted to explain this o-Ps lifetime phenomena was Richard Ferrel. He studied Ps in a liquid helium. Ferrel suggested that the Ps atom forms a nano-bubble around itself.

Later on Ferrel's idea was developed by Samuel Tao and Morten Eldrup. They generalized the problem towards the case of an infinite structureless media. The repulsive Ps interaction with the media was approximated by a infinitely deep spherically symmetric potential well of radius $R_\infty$.

In order to better understand the math behind the model let's recall to the trivial quantum-chemical problems of a particle in an infinite well.

## Particle in a one-dimentional infinite potential well

Let's solve a Schrödinger equation for a particle located in a potential well with the infinite "walls". This well is described by the potential energy of following kind:

\begin{equation}
  U(x)=\begin{cases}\infty,&amp;\text{$x &lt; 0$;}\\ 0,&amp;\text{$0 \leq x \leq L$;}\\ \infty,&amp;\text{$x &gt; L$.}\end{cases}
  \notag
\end{equation}

where $L$ is the box width and the energy minimum is at the bottom of the box.

<div class="row justify-content-center my-4">
    <div class="col-8 col-md-6">
        {% img w-100 /tao-eldrup-positronium-bubble-model/particle-in-a-box.svg "'Particle in a box'" %}
    </div>
</div>

The stationary state Schrödinger equation is following:

\begin{equation} 
  \hat{H} \psi = E \psi
  \label{eq:schroedinger}
\end{equation}

with the Hamiltonian operator being

\begin{equation} 
  \hat{H} = - \frac{\hbar}{2m} \Delta + U
  \label{eq:hamiltonian}
\end{equation}

substitution of \eqref{eq:hamiltonian} into \eqref{eq:schroedinger} gives us general time-independent Schrödinger equation:

\begin{equation}
  \Delta \psi +\frac{2m}{\hbar^2}\left ( E-U \right ) \psi = 0
  \label{eq:sch_indep}
\end{equation}

Considering the one-dimensional case, where the Laplace operator is just $\Delta = \partial^2/\partial x^2$ the \eqref{eq:sch_indep} equation becomes:

\begin{equation}
  \frac{\partial^2 \psi}{\partial x^2} + \frac{2m}{\hbar^2}\left ( E-U \right ) \psi = 0
  \label{eq:sch_indep_linear}  
\end{equation}

It is easy to show that outside of the well ($x &lt; 0$ and $x&gt;L$) the particle wave function is zero. Let's substitute $U=\infty$ to \eqref{eq:sch_indep_linear} and assume that $E\ll\infty$. We get the following

\begin{equation}
  \psi = \frac{1}{\infty} \frac{\partial^2 \psi}{\partial x^2}
  \notag
\end{equation}

so we conclude that $\psi$ is zero outside the box.

For the region $0 \leq x \leq L$ the potential energy $U$ is zero and the Schrödinger equation \eqref{eq:sch_indep_linear} becomes

\begin{equation}
  \frac{\partial^2 \psi}{\partial x^2} + \frac{2m}{\hbar^2}E\psi = 0
  \label{eq:lin_hom}
\end{equation}

where $m$ is the mass of the particle and $E$ is its energy. We recognize the \eqref{eq:lin_hom} as a linear homogeneous differential equation of the second order with the constant coefficients. The auxiliary equation $\left (s^2 + 2mE\hbar^{-2}s = 0 \right )$ gives us $s_{1,2}=\pm i (2mE)^{1/2}/\hbar$. Therefore,

\begin{equation} 
  \psi = C_1 e^{i \sqrt{2mE}\cdot x/\hbar} + C_2 e^{-i \sqrt{2mE}\cdot x/\hbar}
  \label{eq:sol_gen}  
\end{equation}

Applying the $e^{i\phi} = \cos\phi+ i\sin\phi$ we simplify the general solution \eqref{eq:sol_gen} to the following expression, where $A$ and $B$ are new arbitrary constants.

\begin{equation} 
  \psi = A \cos \left( \sqrt{2mE}\cdot x/\hbar \right ) + B \sin \left( \sqrt{2mE}\cdot x/\hbar \right )
  \label{eq:sol_gen_2}
\end{equation}

One of the fundamental properties of the wave function is it has to be continious. We apply two boundary conditions at $x=0$ and $x=L$. First, substitution of $\psi(0) = 0$ gives us $A=0$. With this \eqref{eq:sol_gen_2} becomes

\begin{equation}
  \psi = B \sin \left( \sqrt{2mE}\cdot x/\hbar \right )
  \label{eq:sol_gen_3}  
\end{equation}

Applying the continuity condition at $x=L$, and solving a trivial trigonometric equation we obtain $E = n^2 \pi^2 \hbar^2/ (2mL^2)$, where $n = 1, 2, 3$... Our expression for $\psi$ function \eqref{eq:sol_gen_3} turns into:

\begin{equation}
  \psi = B \sin \left( \frac{n \pi x}{L} \right ), n=1,2,3...
  \label{eq:sol_gen_4}
\end{equation}

In order to find the value for $B$ constant we apply the normalization condition $\int_0^L \left | \psi(x) \right | ^2 dx = 1$. After taking the definite integral we obtain $B=\sqrt{2/L}$. Finally the value for the $\psi$ function is given by the following expression.

\begin{equation}
  \psi = \sqrt{\frac{2}{L}} \sin \left( \frac{n \pi x}{L} \right ), n=1,2,3...
  \label{eq:psi_solution}  
\end{equation}

## Particle in a spherically symmetric infinite potential well

Now having solved the problem of a particle in one-dimensional well let's move on to the particle in a spherically symmetric infinite potential well. By this we mean a particle subjected to a potential energy function that is infinite everywhere outside of the sphere of a radius $R$. Inside the sphere the potential is equal to zero.

<div class="row justify-content-center my-4">
    <div class="col-8 col-md-6">
        {% img w-100 /tao-eldrup-positronium-bubble-model/particle-in-a-sphere.svg "'Particle in a sphere'" %}
    </div>
</div>

In this case the potential energy depends only on the distance to the center of the sphere

\begin{equation} 
  U = U(r)
  \label{eq:pot_sph}  
\end{equation}

It is handy to apply spherical coordinates. Notice that in our case the potential does not depend on the azimuthal and zenith angles. In this case the Laplace operator is

\begin{equation} \label{eq:lap_sph}
  \Delta \psi = \frac{1}{r} \frac {\partial^2}{\partial r^2} r \psi
\end{equation}

Now let's substitute these \eqref{eq:pot_sph} and \eqref{eq:lap_sph} into the general Schrödinger equation \eqref{eq:sch_indep}.

\begin{equation}
  \frac{1}{r} \frac{\partial^2}{\partial r^2} r\psi + \frac{2m}{\hbar}\left( E - U \right ) \psi = 0
\end{equation}

Additionally let's perform a variable substitution in our wave function $\psi = \xi / r$:

\begin{equation}
  \frac{1}{r} \frac{\partial^2}{\partial r^2} \xi + \frac{2m}{\hbar}\left( E - U \right ) \frac {\xi}{r} = 0
\end{equation}

Now notice that if we multiply both sides of this equation by $r$ we will come towards the equation identical to the one in the particle in one-dimensional infinite well (having $\xi$ instead of $\psi$ and $r$ versus $x$:

\begin{equation}
  \frac{\partial^2}{\partial r^2} \xi + \frac{2m}{\hbar}\left( E - U \right ) \xi = 0
\end{equation}

Let's copy the solution from the previous problem \eqref{eq:sol_gen_3}.

\begin{equation}
  \xi = A \cos \left( \sqrt{2mE}\cdot r/\hbar \right ) + B \sin \left( \sqrt{2mE}\cdot r/\hbar \right )
\end{equation}

We get back to our initial wave function variable

\begin{equation}
  \psi = \frac{\xi}{r} = A \frac{1}{r} \cos\left( \sqrt{2mE}\cdot r/\hbar \right ) + B \frac{1}{r} \sin\left( \sqrt{2mE}\cdot r/\hbar \right )
  \label{eq:psi_sphere}
\end{equation}

Here if we consider the wave function in the center of the sphere $(r=0)$ it turns out that the first member of the wave function \eqref{eq:psi_sphere} goes to infinity

\begin{equation}
  \lim_{r\to 0} A \frac{\cos\left( \sqrt{2mE}\cdot r/\hbar \right )}{r} \to \infty
  \label{eq:psi_sphere_2}  
\end{equation}

which contradicts the fundamental continuity wave function principle. Thus, we fix the $A$ coefficient to zero and \eqref{eq:psi_sphere} turns into

\begin{equation}
  \psi = B \frac{1}{r} \sin\left( \sqrt{2mE}\cdot r/\hbar \right )
  \notag
\end{equation}

Next we apply the boundary condition $\psi(R)=0$. Similar to the first problem, we get $E = n^2 \pi^2 \hbar^2/ (2mR^2)$, where $n \in \cal{N}$ and our expression for $\psi$ function \eqref{eq:psi_sphere} becomes

\begin{equation}
  \psi = B \frac {1}{r} \sin \left( \frac{n \pi r}{R} \right ), n=1,2,3...
  \label{eq:psi_sphere_3}  
\end{equation}

Apparently in order to normalize the wave function we need to take a definite integral of \eqref{eq:sol_gen_4} over the sphere $\int_0^R 4\pi r^2 \left | \psi(x) \right | ^2 dr = 1$. The integration process gives us $B=(2 \pi R)^{-1/2}$. Thus the final solution for the $\psi$ function is following

\begin{equation}
  \psi = \frac {\sin \left( \frac{n \pi r }{R} \right )}{\sqrt{2\pi R}r}, n=1,2,3...
  \label{eq:psi_sphere_final}
\end{equation}

## Estimating the Ps bubble radius

Previously we mentioned that R. Ferrel brought up the idea that Ps atom forms a bubble of a radius $R_\infty$ around itself. In order to estimate equilibrium radius of the Ps bubble he minimized the sum of the positronium energy in a spherically symmetric potential well (stands for the bubble growth) and its macroscopic surface energy (that tends to collapse the bubble).

\begin{equation} \label{eq:ferrel}
E = E_{\rm Ps} + E_{\rm surface} \to \text{minimize over} R_\infty
\end{equation}

First let's calculate the positronium energy. We just have to apply a Hamiltonian operator to positronium wave function \eqref{eq:psi_sphere_final}. We consider Ps in a ground state which means we fix $n=1$.

\begin{equation}
  \hat{H}\psi = \left ( -\frac{\hbar^2}{2m_{\rm Ps}} \Delta + U \right ) \psi
  \notag
\end{equation}

We use the positronium wave function from \eqref{eq:psi_sphere_final}. Remember that the potential energy inside the sphere is zero and the Laplace operator in spherical coordinates is $\Delta = 1/r \cdot \partial^2/\partial r^2 ( r \psi)$. So we get:

\begin{equation}
  \hat{H}\psi = -\frac{\hbar^2}{2m_{\rm Ps}} \frac{1}{r} \frac{\partial^2}{\partial r^2}\left ( r \cdot \frac {\sin \left( \pi r / R_\infty \right )}{\sqrt{2\pi R}r} \right ) = \frac{\hbar^2\pi^2}{2m_{\rm Ps}R^2_\infty} \psi
\end{equation}

It's clear that positronium energy eigenvalue above is:

\begin{equation} 
  E_{\rm Ps} = \frac{\hbar^2\pi^2}{2m_{\rm Ps}R^2_\infty} = \frac{\hbar^2\pi^2}{4mR^2_\infty} = \frac{\pi^2 a_0^2}{2R_\infty^2} {\rm Ry}
  \label{eq:ps_energy}
\end{equation}

where $m$ is a mass of an electron, ${\rm Ry} = me^4/e\hbar^2 = 13.6$ eV is a Rydberg constant and $a_0 = \hbar^2/me^2 = 0.53 $ Å is a Bohr radius.

Secondly, the macroscopic surface tension energy is simply

\begin{equation}
  E_{\rm surface} = 4\pi R_\infty^2 \sigma
  \label{eq:surface_energy}
\end{equation}

where $\sigma$ is the macroscopic surface tension coefficient. Next we substitute the Ps atom energy \eqref{eq:ps_energy} that stands for the bubble growth and the surface tension energy \eqref{eq:surface_energy} into \eqref{eq:ferrel} and minimize it over $R_\infty$:

\begin{equation} 
  E = E_{\rm Ps} + E_{\rm surface} \to \text{minimize over} R_\infty
  \label{eq:ferrel2}
\end{equation}

Finally we get the equation for the Ps bubble radius:

\begin{equation}
  R_\infty = a_0 \left ( \frac{\pi {\rm Ry}}{8 \sigma a_0^2}\right ) ^{1/4}
  \label{eq:bubble_radius}
\end{equation}

## Tao-Eldrup positron bubble model

Tao and Eldrup et al. considered the Ps atom as a point particle in a structureless continuum. The repulsive Ps-media interaction was approximated by an infinitely deep spherically symmetric potential well of radius $R_\infty$. In order for the pick-off annihilation possible to teke place we must allow penetration of the molecular electrons inside the sphere. We introduce a border layer inside the sphere of a thickness $\delta = R_\infty - R$ that is occupied by molecular electrons. Here $R$ is the free volume radius of the Ps bubble. The wave function $\psi(r)$ is the center-of-mass wave function of Ps atom.

<div class="row justify-content-center my-4">
    <div class="col-8 col-md-6">
        {% img w-100 /tao-eldrup-positronium-bubble-model/tao-eldrup-1.svg "''" %}
    </div>
</div>

We've just derived the expression for the wave function of a point particle in this well. Here we use $R_\infty$ instead or $R$ in \eqref{eq:psi_sphere_final}. Also we set $n=1$ because we consider the Ps atom in the ground state.

\begin{equation}
  \psi(0\le r\le R_\infty) = \frac {\sin \left( \frac{\pi r}{R_\infty} \right )}{\sqrt{2\pi R_\infty}r}, \psi(r\ge R_\infty) = 0
  \label{eq:tao_psi}  
\end{equation}

The pick-off annihilation rate $\lambda_{po}$ is proportional to the overlapping integral of a positronium wave function and the electron layer inside the bubble. Additionally we assume that the electron density in the border layer is the same as in the bulk material. Then the annihilation rate $\lambda_{po}$ inside the layer will be also proportional to the positron annihilation rate in an unperturbed medium $\lambda_+ \approx 2 ns^{-1}$.

\begin{equation}
  \lambda_{po} = \lambda_+ \int_R^{R_\infty} \left | \psi(r)\right |^2 4\pi r^2 dr
  \label{eq:tao_rate}
\end{equation}

Substitution of the positronium wave function \eqref{eq:tao_psi} and subsequent integration of \eqref{eq:tao_rate} gives Tao-Eldrup equation:

\begin{equation}
  \lambda_{po} = \lambda_+ \left [ 1 - \frac{R}{R_\infty} + \frac{1}{2\pi} \sin\left ( \frac{2\pi R}{R_\infty} \right ) \right ]
  \label{eq:tao_R}
\end{equation}

As far as $R = R_\infty - \delta$, the above equation is equal to:

\begin{equation}
  \lambda_{po} = \lambda_+ \left [ \frac{\delta}{R_\infty} - \frac{1}{2\pi} \sin\left ( \frac{2\pi \delta}{R_\infty} \right ) \right ]
  \label{eq:tao_delta}
\end{equation}

Substituting \eqref{eq:bubble_radius} for $R_\infty$ into \eqref{eq:tao_delta}, we obtain the relationship between $\lambda_{po}$ and $\sigma$ with one adjustable parameter, $\delta$. It may be easily obtained by fitting experimental pick-off annihilation rate constants with the relationship \eqref{eq:tao_delta}, see figure.

<figure class="row justify-content-center my-4">
    <div class="col-8 col-md-6">
        {% img "w-100 mb-4" /tao-eldrup-positronium-bubble-model/pick-off.svg "'Dependence of the pick-off annihilation rates [8] vs. surface tension in different liquids'" %}
    </div>
    <figcaption class="col col-md-10">Dependence of the pick-off annihilation rates vs. surface tension in different liquids. Solid curve shows the correlation given by the Tao-Eldrup at λ+ = 2 ns−1 and optimal value $\delta=1.66$ Å (obtained from fitting of this data by means of Eq. \eqref{eq:tao_delta}). Dashed curve illustrates simplest approximation $\lambda_{po} \propto \sigma^{1/2}$.</figcaption>
</figure>

From the fit we obtain $\delta = 1.66$ Å. Equation \eqref{eq:tao_R} with this value of $\delta$ is widely used for recalculation of the observed pick-off annihilation rate into the free volume $4\pi R^3/3$ of the cavity, where Ps atom resides and annihilates.:

\begin{equation}
  \lambda_{po} = \frac{1}{\tau_{po}} = 2 \left [ 1 - \frac{R}{R+1.66} + \frac{1}{2\pi} \sin\left ( \frac{2\pi R}{R + 1.66} \right ) \right ]
\end{equation}

A MatLab file that solves the above equation for the R variable taking the can be downloaded <a href="https://app.box.com/s/fmnzx66o4q4tio11e53f28ovn2ct2c8u">here</a>.