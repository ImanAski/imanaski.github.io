
prove that

$$

\frac{dP_{ab}}{dt} = J(a,t) - J(b,t)

$$


where

$$

J(x,t) = \frac{i\hbar}{2m}(\Psi\frac{\partial{\Psi^{*}}}{\partial{x}}-\Psi^{*}\frac{\partial{\Psi}}{\partial{x}})

$$

  
$$

P_{ab}=\int_{a}^{b}\rho(x)dx

$$

Tip for Iman, cause you retarded

$$

\frac{d}{dx}(fg)=f\frac{dg}{dx}+\frac{df}{dx}g

$$

solution:
$$

\frac{dP_{ab}}{dt}=\frac{d}{dt}\int_{a}^{b}\Psi^{*}(x,t)\Psi(x,t)dx=\int_{a}^{b}\frac{\partial}{\partial{t}}(\Psi^{*}\Psi)

$$

$$

\frac{dP_{ab}}{dt}=\int_{a}^{b}(\Psi^{*}\frac{\partial{\Psi}}{dt}+\Psi\frac{\partial{\Psi^{*}}}{\partial{t}})dx

$$

for $\frac{\partial{\Psi}}{\partial{t}}$ and $\frac{\partial{\Psi^{*}}}{\partial{t}}$ we shall use the Schrodinger equation to obtain them, thus:

$$

i\hbar\frac{\partial{\Psi}}{\partial{t}}=\hat{H}\Psi \quad \textrm{H is Hamiltonian}

$$
$$

\hat{H}=-\frac{\hbar^{2}}{2m}\frac{\partial^{2}}{\partial{x^{2}}}+V(x)

$$
$$

\frac{\partial{\Psi}}{\partial{t}}=\frac{1}{i\hbar}\hat{H}\Psi=\frac{1}{i\hbar}(-\frac{h^{2}}{2m}\frac{\partial^{2}}{\partial{x^{2}}}+V\Psi)=\frac{i\hbar}{2m}\frac{\partial^{2}{\Psi}}{\partial{x^{2}}}+\frac{i}{\hbar}V\Psi

$$
$$

\frac{\partial{\Psi^{*}}}{\partial{t}}=\frac{1}{i\hbar}\hat{H}\Psi^{*}=\frac{1}{i\hbar}(-\frac{h^{2}}{2m}\frac{\partial^{2}}{\partial{x^{2}}}+V\Psi^{*})=\frac{i\hbar}{2m}\frac{\partial^{2}{\Psi^{*}}}{\partial{x^{2}}}+\frac{i}{\hbar}V\Psi^{*}

$$
Now that we have them, we should continue:
$$

\frac{\partial}{\partial{t}}(\Psi^{*}\Psi)=\Psi^{*}(\frac{i\hbar}{2m}\frac{\partial^{2}{\Psi}}{\partial{x^{2}}}-\frac{i}{\hbar}V\Psi)+\Psi(-\frac{i\hbar}{2m}\frac{\partial^{2}{\Psi^{*}}}{\partial{x^{2}}}-\frac{i}{\hbar}V\Psi^{*})

$$
We factorized this by common:
$$

\frac{i\hbar}{2m}(\Psi^{*}\frac{\partial^{2}\Psi}{\partial{x^{2}}}-\Psi\frac{\partial^{2}\Psi^{*}}{\partial{x^{2}}})+\frac{i}{\hbar}V(\Psi\Psi^{*}-\Psi^{*}\Psi)

$$
Since $\Psi\Psi^{*}-\Psi^{*}\Psi=0$ then, the equations have become:
$$

\frac{\partial}{\partial{t}}(\Psi^{*}\Psi)=\frac{i\hbar}{2m}(\Psi^{*}\frac{\partial^{2}\Psi}{\partial{x^{2}}}-\Psi\frac{\partial^{2}\Psi^{*}}{\partial{x^{2}}})

$$

  

Now we can use this as:

  

$$

\frac{dP_{ab}}{dt}=\int_{a}^{b}\frac{i\hbar}{2m}(\Psi^{*}\frac{\partial^{2}\Psi}{\partial{x^{2}}}-\Psi\frac{\partial^{2}\Psi^{*}}{\partial{x^{2}}})dx

$$
Now evaluate J as:
$$

J(x,t)=\frac{i\hbar}{2m}(\Psi\frac{\partial{\Psi^{*}}}{\partial{x}}-\Psi^{*}\frac{\partial{\Psi}}{\partial{x}})

$$
We should determine the spatial derivative of J according to x:
$$

\frac{\partial{J}}{\partial{x}}=\frac{\partial}{\partial{x}}[\frac{i\hbar}{2m}(\Psi\frac{\partial{\Psi^{*}}}{\partial{x}}-\Psi^{*}\frac{\partial{\Psi}}{\partial{x}})]=\frac{i\hbar}{2m}(\frac{\partial{\Psi}}{\partial{x}}\frac{\partial{\Psi^{*}}}{\partial{x}}+\Psi\frac{\partial^{2}{\Psi^{*}}}{\partial{x^{2}}}-\Psi^{*}\frac{\partial^{2}\Psi}{\partial{x^{2}}})

$$
so it becomes:
$$

\frac{i\hbar}{2m}(\Psi\frac{\partial^{2}{\Psi^{*}}}{\partial{x^{2}}}-\Psi^{*}\frac{\partial^{2}{\Psi}}{\partial{x^{2}}})

$$
So we can conclude that:
$$

\frac{\partial}{\partial{t}}(\Psi^{*}\Psi)=-\frac{\partial{J}}{\partial{x}}

$$
$$

\frac{dP_{ab}}{dt}=\int_{a}^{b}(-\frac{\partial{J}}{\partial{x}})dx= -\int_{a}^{b}\frac{\partial{J}}{\partial{x}}=-[J(x,t)]_{a}^{b}=J(a,t)-J(b,t)

$$
so finally
$$

\frac{dP_{ab}}{dt}=J(a,t)-J(b,t)

$$