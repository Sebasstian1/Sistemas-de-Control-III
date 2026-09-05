# Análisis de un Circuito RLC en Serie

## Integrantes

- Nombre del integrante 1
- Nombre del integrante 2
- Nombre del integrante 3

---

## Introducción

Un circuito RLC en serie está formado por una resistencia $R$, una inductancia $L$ y un capacitor $C$ conectados en serie.

Este circuito es un sistema eléctrico de segundo orden y puede utilizarse para estudiar conceptos fundamentales de sistemas de control, como ecuaciones diferenciales, transformada de Laplace, función de transferencia, polos, amortiguamiento y respuesta temporal.

En este documento se obtiene el modelo matemático del circuito utilizando la Ley de Kirchhoff de Voltajes. Posteriormente se aplica la transformada de Laplace para obtener la función de transferencia entre el voltaje de entrada y el voltaje de salida.

Las variables utilizadas son:

- $e_i(t)$: voltaje de entrada.
- $e_o(t)$: voltaje de salida.
- $v_R(t)$: voltaje en la resistencia.
- $v_L(t)$: voltaje en el inductor.
- $E_i(s)$: voltaje de entrada en el dominio de Laplace.
- $E_o(s)$: voltaje de salida en el dominio de Laplace.
- $i(t)$: corriente del circuito.
- $q(t)$: carga eléctrica.
- $R$: resistencia.
- $L$: inductancia.
- $C$: capacitancia.

---

# 1. Circuito RLC

A continuación se muestra el circuito RLC en serie utilizado para realizar el análisis.

![Circuito RLC en serie](circuito-rlc.png)

**Figura 1.** Circuito RLC en serie.

El circuito está compuesto por una resistencia $R$, un inductor $L$ y un capacitor $C$ conectados en serie.

El voltaje de entrada se representa mediante $e_i(t)$.

El voltaje de salida $e_o(t)$ corresponde al voltaje medido en el capacitor.

Por lo tanto:

$$e_o(t)=\frac{q(t)}{C}$$

Debido a que los elementos están conectados en serie, la misma corriente $i(t)$ circula por la resistencia, el inductor y el capacitor.

El objetivo es obtener una relación matemática entre el voltaje de entrada $e_i(t)$ y el voltaje de salida $e_o(t)$.

---

# 2. Elementos del Circuito

## 2.1 Resistencia

La resistencia es el elemento que se opone al paso de la corriente eléctrica y disipa energía en forma de calor.

La relación entre el voltaje y la corriente está dada por la Ley de Ohm:

$$v_R(t)=Ri(t)$$

La resistencia influye directamente en el amortiguamiento del sistema.

Un aumento en el valor de $R$ produce un mayor amortiguamiento y reduce la tendencia del circuito a presentar oscilaciones.

---

## 2.2 Inductor

El inductor almacena energía en forma de campo magnético.

El voltaje en el inductor está dado por:

$$v_L(t)=L\frac{di(t)}{dt}$$

donde $L$ representa la inductancia.

El inductor introduce una relación entre el voltaje y la variación de la corriente.

---

## 2.3 Capacitor

El capacitor almacena energía en forma de campo eléctrico.

El voltaje del capacitor corresponde al voltaje de salida:

$$e_o(t)=\frac{q(t)}{C}$$

donde $q(t)$ representa la carga eléctrica.

La corriente está relacionada con la variación de la carga mediante:

$$i(t)=\frac{dq(t)}{dt}$$

Como:

$$q(t)=Ce_o(t)$$

se obtiene:

$$i(t)=C\frac{de_o(t)}{dt}$$

Esta relación será utilizada para obtener la ecuación diferencial del sistema.

---

# 3. Ley de Kirchhoff de Voltajes

Para obtener el modelo matemático se utiliza la Ley de Kirchhoff de Voltajes.

Esta ley establece que la suma de las caídas de voltaje en una malla es igual al voltaje aplicado.

Para el circuito RLC:

$$e_i(t)=v_R(t)+v_L(t)+e_o(t)$$

Donde $v_R(t)$ es el voltaje en la resistencia, $v_L(t)$ es el voltaje en el inductor y $e_o(t)$ es el voltaje de salida tomado en el capacitor.

Sustituyendo las ecuaciones de cada componente:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Esta expresión representa la suma de los voltajes presentes en los tres elementos del circuito.

---

# 4. Obtención de la Ecuación Diferencial

Sabemos que la corriente del capacitor es:

$$i(t)=C\frac{de_o(t)}{dt}$$

Derivando respecto al tiempo:

$$\frac{di(t)}{dt}=C\frac{d^2e_o(t)}{dt^2}$$

Partimos nuevamente de la Ley de Kirchhoff:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Sustituyendo la corriente:

$$e_i(t)=RC\frac{de_o(t)}{dt}+LC\frac{d^2e_o(t)}{dt^2}+e_o(t)$$

Ordenando los términos:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Por lo tanto, la ecuación diferencial del sistema es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Esta ecuación diferencial describe el comportamiento dinámico del circuito RLC.

Es una ecuación diferencial lineal de segundo orden debido a que contiene la segunda derivada del voltaje de salida.

---

# 5. Ecuación Diferencial Normalizada

La ecuación diferencial obtenida es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Dividiendo todos los términos entre $LC$:

$$\frac{d^2e_o(t)}{dt^2}+\frac{R}{L}\frac{de_o(t)}{dt}+\frac{1}{LC}e_o(t)=\frac{1}{LC}e_i(t)$$

Esta forma permite comparar el circuito con la forma estándar de un sistema de segundo orden.

---

# 6. Condiciones Iniciales

Para resolver completamente la ecuación diferencial es necesario conocer las condiciones iniciales.

El voltaje inicial del capacitor se representa mediante:

$$e_o(0)=e_{o0}$$

La corriente inicial del circuito se representa mediante:

$$i(0)=i_0$$

Como:

$$i(t)=C\frac{de_o(t)}{dt}$$

entonces:

$$i(0)=Ce_o'(0)$$

Por lo tanto:

$$e_o'(0)=\frac{i_0}{C}$$

Para obtener la función de transferencia normalmente se consideran condiciones iniciales cero:

$$e_o(0)=0$$

$$i(0)=0$$

---

# 7. Transformada de Laplace

La transformada de Laplace permite convertir una ecuación diferencial del dominio del tiempo en una ecuación algebraica en el dominio de la variable $s$.

La ecuación diferencial del circuito es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Para realizar la transformación se utilizan las siguientes relaciones:

$$L\{e_o(t)\}=E_o(s)$$

$$L\{\frac{de_o(t)}{dt}\}=sE_o(s)-e_o(0)$$

$$L\{\frac{d^2e_o(t)}{dt^2}\}=s^2E_o(s)-se_o(0)-e_o'(0)$$

Para el voltaje de entrada:

$$L\{e_i(t)\}=E_i(s)$$

Estas relaciones permiten transformar cada término de la ecuación diferencial al dominio de Laplace.

---

# 8. Aplicación de la Transformada de Laplace

Aplicando la transformada de Laplace a la ecuación diferencial:

$$LC[s^2E_o(s)-se_o(0)-e_o'(0)]+RC[sE_o(s)-e_o(0)]+E_o(s)=E_i(s)$$

Distribuyendo los términos:

$$LCs^2E_o(s)-LCse_o(0)-LCe_o'(0)+RCsE_o(s)-RCe_o(0)+E_o(s)=E_i(s)$$

Agrupando los términos que contienen $E_o(s)$:

$$E_o(s)[LCs^2+RCs+1]=E_i(s)+LCse_o(0)+LCe_o'(0)+RCe_o(0)$$

Despejando $E_o(s)$:

$$E_o(s)=\frac{E_i(s)+LCse_o(0)+LCe_o'(0)+RCe_o(0)}{LCs^2+RCs+1}$$

Esta expresión representa el sistema considerando condiciones iniciales generales.

---

# 9. Condiciones Iniciales Cero

Para obtener la función de transferencia se consideran condiciones iniciales cero:

$$e_o(0)=0$$

$$e_o'(0)=0$$

Entonces:

$$E_o(s)[LCs^2+RCs+1]=E_i(s)$$

Despejando:

$$E_o(s)=\frac{E_i(s)}{LCs^2+RCs+1}$$

Por lo tanto, la función de transferencia del circuito es:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

Esta función representa la relación entre el voltaje de salida y el voltaje de entrada en el dominio de Laplace.

---

# 10. Forma Normalizada de la Función de Transferencia

La función de transferencia es:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

Dividiendo entre $LC$:

$$\frac{E_o(s)}{E_i(s)}=\frac{\frac{1}{LC}}{s^2+\frac{R}{L}s+\frac{1}{LC}}$$

La forma estándar de un sistema de segundo orden es:

$$\frac{E_o(s)}{E_i(s)}=\frac{\omega_n^2}{s^2+2\zeta\omega_ns+\omega_n^2}$$

Comparando ambas expresiones:

$$\omega_n^2=\frac{1}{LC}$$

Por lo tanto:

$$\omega_n=\frac{1}{\sqrt{LC}}$$

Además:

$$2\zeta\omega_n=\frac{R}{L}$$

De esta relación:

$$\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}$$

---

# 11. Ecuación Característica

La ecuación característica se obtiene a partir del denominador de la función de transferencia:

$$LCs^2+RCs+1=0$$

Dividiendo entre $LC$:

$$s^2+\frac{R}{L}s+\frac{1}{LC}=0$$

Las raíces de esta ecuación representan los polos del sistema.

Los polos permiten determinar el comportamiento dinámico del circuito.

---

# 12. Parámetros del Sistema

La frecuencia natural no amortiguada es:

$$\omega_n=\frac{1}{\sqrt{LC}}$$

El factor de amortiguamiento es:

$$\alpha=\frac{R}{2L}$$

El factor de amortiguamiento relativo es:

$$\zeta=\frac{\alpha}{\omega_n}$$

También puede escribirse como:

$$\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}$$

Cuando el sistema es subamortiguado, la frecuencia amortiguada es:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

---

# 13. Tipos de Respuesta

El comportamiento del circuito depende de la relación entre $\alpha$ y $\omega_n$.

## Sistema Subamortiguado

Se presenta cuando:

$$\alpha<\omega_n$$

Equivalentemente:

$$R<2\sqrt{\frac{L}{C}}$$

Los polos son complejos conjugados:

$$s_{1,2}=-\alpha\pm j\omega_d$$

La frecuencia amortiguada es:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

El sistema presenta oscilaciones que disminuyen progresivamente con el tiempo.

La respuesta natural tiene la forma:

$$e_{on}(t)=e^{-\alpha t}[A\cos(\omega_dt)+B\sin(\omega_dt)]$$

---

## Sistema Críticamente Amortiguado

Se presenta cuando:

$$\alpha=\omega_n$$

Equivalentemente:

$$R=2\sqrt{\frac{L}{C}}$$

Los polos son reales e iguales:

$$s_1=s_2=-\alpha$$

La respuesta natural tiene la forma:

$$e_{on}(t)=(A+Bt)e^{-\alpha t}$$

El sistema regresa al equilibrio sin presentar oscilaciones.

---

## Sistema Sobreamortiguado

Se presenta cuando:

$$\alpha>\omega_n$$

Equivalentemente:

$$R>2\sqrt{\frac{L}{C}}$$

Los polos son reales y diferentes:

$$s_{1,2}=-\alpha\pm\sqrt{\alpha^2-\omega_n^2}$$

El sistema no presenta oscilaciones.

---

# 14. Entrada Escalón

Para analizar la respuesta del circuito ante una entrada escalón se utiliza:

$$e_i(t)=E_0u(t)$$

La transformada de Laplace de la entrada es:

$$E_i(s)=\frac{E_0}{s}$$

Utilizando la función de transferencia:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

se obtiene:

$$E_o(s)=\frac{E_0}{s[LCs^2+RCs+1]}$$

La respuesta temporal dependerá de los valores de $R$, $L$ y $C$.

---

# 15. Respuesta Temporal del Sistema Subamortiguado

Para un sistema subamortiguado con condiciones iniciales cero y una entrada escalón, la respuesta del voltaje de salida es:

$$e_o(t)=E_0[1-e^{-\alpha t}[\cos(\omega_dt)+\frac{\alpha}{\omega_d}\sin(\omega_dt)]]$$

donde:

$$\alpha=\frac{R}{2L}$$

y:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

Esta expresión representa la respuesta transitoria y permanente del voltaje del capacitor.

El término $e^{-\alpha t}$ representa el decaimiento de la respuesta debido al amortiguamiento.

Los términos $\cos(\omega_dt)$ y $\sin(\omega_dt)$ representan el comportamiento oscilatorio del sistema.

---

# 16. Corriente del Circuito

La corriente está relacionada con el voltaje de salida mediante:

$$i(t)=C\frac{de_o(t)}{dt}$$

Para un sistema subamortiguado y una entrada escalón:

$$i(t)=\frac{E_0}{L\omega_d}e^{-\alpha t}\sin(\omega_dt)$$

La corriente presenta una respuesta oscilatoria amortiguada.

Con el paso del tiempo:

$$i(t)\rightarrow0$$

Esto ocurre porque, en estado estacionario de corriente continua, el capacitor se comporta como un circuito abierto.

---

# 17. Valor Final

Para una entrada escalón de amplitud $E_0$, el voltaje de salida alcanza finalmente:

$$e_o(\infty)=E_0$$

La carga almacenada en el capacitor está dada por:

$$q(t)=Ce_o(t)$$

Por lo tanto, la carga final es:

$$q(\infty)=CE_0$$

La corriente final es:

$$i(\infty)=0$$

Esto demuestra que el capacitor termina cargándose hasta alcanzar el voltaje de entrada.

---

# 18. Interpretación Física

El comportamiento del circuito RLC se debe al intercambio de energía entre el inductor y el capacitor.

El capacitor almacena energía en forma de campo eléctrico, mientras que el inductor almacena energía en forma de campo magnético.

La resistencia disipa parte de esta energía en forma de calor.

Cuando el circuito es subamortiguado, la energía se intercambia entre el inductor y el capacitor, produciendo oscilaciones en la respuesta.

La resistencia provoca que estas oscilaciones disminuyan progresivamente hasta que el sistema alcanza el estado estacionario.

Por lo tanto, cada componente tiene una función específica:

- La resistencia $R$ disipa energía y determina el amortiguamiento.
- El inductor $L$ almacena energía magnética.
- El capacitor $C$ almacena energía eléctrica.
- El capacitor proporciona el voltaje de salida $e_o(t)$.

---

# 19. Resumen del Modelo Matemático

La ecuación diferencial del sistema es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

La ecuación diferencial normalizada es:

$$\frac{d^2e_o(t)}{dt^2}+\frac{R}{L}\frac{de_o(t)}{dt}+\frac{1}{LC}e_o(t)=\frac{1}{LC}e_i(t)$$

La ecuación característica es:

$$LCs^2+RCs+1=0$$

La frecuencia natural es:

$$\omega_n=\frac{1}{\sqrt{LC}}$$

El factor de amortiguamiento es:

$$\alpha=\frac{R}{2L}$$

El factor de amortiguamiento relativo es:

$$\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}$$

La frecuencia amortiguada es:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

La función de transferencia es:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

---

# 20. Conclusiones

El análisis del circuito RLC en serie permitió obtener un modelo matemático que describe la relación entre el voltaje de entrada $e_i(t)$ y el voltaje de salida $e_o(t)$.

A partir de las ecuaciones de la resistencia, el inductor y el capacitor, junto con la Ley de Kirchhoff de Voltajes, se obtuvo una ecuación diferencial de segundo orden:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Posteriormente, mediante la transformada de Laplace, la ecuación diferencial se convirtió en una ecuación algebraica en el dominio de $s$. Considerando condiciones iniciales cero, se obtuvo la función de transferencia:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

La función de transferencia permite analizar el comportamiento del circuito y determinar sus polos y características dinámicas.

Los parámetros $\omega_n$, $\alpha$ y $\zeta$ permiten identificar el tipo de respuesta del sistema y determinar si el circuito es subamortiguado, críticamente amortiguado o sobreamortiguado.

El análisis también permite comprender la función de cada componente. La resistencia disipa energía, el inductor almacena energía magnética y el capacitor almacena energía eléctrica y proporciona el voltaje de salida.

En conclusión, el circuito RLC en serie constituye un ejemplo práctico de un sistema dinámico de segundo orden y permite aplicar conceptos fundamentales de sistemas de control como ecuaciones diferenciales, transformada de Laplace, función de transferencia, polos y análisis de estabilidad.
