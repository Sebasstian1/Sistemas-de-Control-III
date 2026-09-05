# Análisis de un Circuito RLC en Serie

## Introducción

Un circuito RLC en serie es un sistema eléctrico formado por una resistencia $R$, una inductancia $L$ y un capacitor $C$ conectados en serie.

Este tipo de circuito es importante en el estudio de sistemas de control porque su comportamiento puede describirse mediante una ecuación diferencial de segundo orden.

El análisis del circuito permite estudiar conceptos como la función de transferencia, los polos, la estabilidad, el amortiguamiento, la frecuencia natural y la respuesta temporal.

En este proyecto se obtiene el modelo matemático del circuito RLC a partir de la Ley de Kirchhoff de Voltajes. Posteriormente, se aplica la transformada de Laplace para obtener la función de transferencia entre el voltaje de entrada y el voltaje de salida.

Las variables utilizadas son:

- $e_i(t)$: voltaje de entrada.
- $e_o(t)$: voltaje de salida.
- $E_i(s)$: transformada de Laplace del voltaje de entrada.
- $E_o(s)$: transformada de Laplace del voltaje de salida.
- $i(t)$: corriente del circuito.
- $q(t)$: carga eléctrica.
- $R$: resistencia.
- $L$: inductancia.
- $C$: capacitancia.

---

# 1. Circuito RLC en Serie

Un circuito RLC en serie está formado por tres elementos eléctricos:

- Una resistencia $R$.
- Una inductancia $L$.
- Un capacitor $C$.

Los tres elementos están conectados en serie, por lo que la misma corriente $i(t)$ circula por todos ellos.

El voltaje aplicado al circuito se representa mediante $e_i(t)$.

Para este análisis, el voltaje de salida $e_o(t)$ se considera como el voltaje medido en el capacitor.

Por lo tanto:

$$e_o(t)=\frac{q(t)}{C}$$

El objetivo es encontrar una relación matemática entre el voltaje de entrada $e_i(t)$ y el voltaje de salida $e_o(t)$.

---

# 2. Elementos del Circuito

## 2.1 Resistencia

La resistencia es el elemento que se opone al paso de la corriente eléctrica y disipa energía en forma de calor.

La relación entre el voltaje y la corriente en una resistencia está dada por la Ley de Ohm:

$$e_R(t)=Ri(t)$$

La resistencia influye directamente en el amortiguamiento del sistema.

Cuando aumenta el valor de $R$, aumenta el amortiguamiento del circuito y disminuye la tendencia a presentar oscilaciones.

---

## 2.2 Inductor

El inductor almacena energía en forma de campo magnético.

El voltaje de un inductor depende de la variación de la corriente con respecto al tiempo:

$$e_L(t)=L\frac{di(t)}{dt}$$

donde $L$ representa la inductancia y se mide en henrios.

El inductor introduce una derivada de la corriente en la ecuación del circuito y contribuye al comportamiento dinámico del sistema.

---

## 2.3 Capacitor

El capacitor almacena energía en forma de campo eléctrico.

El voltaje del capacitor está relacionado con la carga eléctrica mediante:

$$e_o(t)=\frac{q(t)}{C}$$

donde $C$ representa la capacitancia.

La corriente está relacionada con la variación de la carga:

$$i(t)=\frac{dq(t)}{dt}$$

Como:

$$q(t)=Ce_o(t)$$

derivando:

$$\frac{dq(t)}{dt}=C\frac{de_o(t)}{dt}$$

Por lo tanto:

$$i(t)=C\frac{de_o(t)}{dt}$$

Esta relación será utilizada para expresar toda la ecuación del circuito en función de la entrada y la salida.

---

# 3. Ley de Kirchhoff de Voltajes

Para obtener el modelo matemático se utiliza la Ley de Kirchhoff de Voltajes.

Esta ley establece que la suma de las caídas de voltaje en una malla es igual al voltaje aplicado.

Para el circuito RLC:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Esta ecuación representa la suma de los voltajes de los tres elementos.

Sin embargo, todavía aparece la corriente $i(t)$.

Como nuestro objetivo es obtener una relación entre la entrada $e_i(t)$ y la salida $e_o(t)$, debemos eliminar la corriente utilizando la ecuación del capacitor.

---

# 4. Obtención de la Ecuación Diferencial

Sabemos que:

$$i(t)=C\frac{de_o(t)}{dt}$$

Derivando esta expresión:

$$\frac{di(t)}{dt}=C\frac{d^2e_o(t)}{dt^2}$$

Ahora sustituimos estas expresiones en la Ley de Kirchhoff:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Sustituyendo la corriente:

$$e_i(t)=RC\frac{de_o(t)}{dt}+LC\frac{d^2e_o(t)}{dt^2}+e_o(t)$$

Ordenando los términos:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Por lo tanto, la ecuación diferencial del sistema es:

$$\boxed{LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)}$$

Esta ecuación representa matemáticamente el comportamiento dinámico del circuito RLC.

Es una ecuación diferencial lineal de segundo orden porque contiene la segunda derivada del voltaje de salida.

---

# 5. Ecuación Diferencial Normalizada

La ecuación diferencial obtenida es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Dividiendo todos los términos entre $LC$:

$$\frac{d^2e_o(t)}{dt^2}+\frac{R}{L}\frac{de_o(t)}{dt}+\frac{1}{LC}e_o(t)=\frac{1}{LC}e_i(t)$$

Esta forma permite comparar el circuito RLC con la forma estándar de un sistema de segundo orden.

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

Las condiciones iniciales pueden expresarse como:

$$e_o(0)=e_{o0}$$

$$e_o'(0)=\frac{i_0}{C}$$

Para obtener la función de transferencia normalmente se consideran condiciones iniciales cero:

$$e_o(0)=0$$

$$e_o'(0)=0$$

---

# 7. Transformada de Laplace

Una vez obtenida la ecuación diferencial, se utiliza la transformada de Laplace para convertir la ecuación del dominio del tiempo al dominio de la variable compleja $s$.

La ecuación diferencial es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

La transformada de Laplace permite convertir las derivadas en expresiones algebraicas.

Para la primera derivada:

$$\mathcal{L}\{\frac{de_o(t)}{dt}\}=sE_o(s)-e_o(0)$$

Para la segunda derivada:

$$\mathcal{L}\{\frac{d^2e_o(t)}{dt^2}\}=s^2E_o(s)-se_o(0)-e_o'(0)$$

Además:

$$\mathcal{L}\{e_o(t)\}=E_o(s)$$

y:

$$\mathcal{L}\{e_i(t)\}=E_i(s)$$

---

# 8. Aplicación de la Transformada de Laplace

Aplicamos la transformada de Laplace a la ecuación diferencial:

$$LC\{\frac{d^2e_o(t)}{dt^2}\}+RC\{\frac{de_o(t)}{dt}\}+E_o(s)=E_i(s)$$

Sustituyendo las transformadas de las derivadas:

$$LC[s^2E_o(s)-se_o(0)-e_o'(0)]+RC[sE_o(s)-e_o(0)]+E_o(s)=E_i(s)$$

Distribuyendo los términos:

$$LCs^2E_o(s)-LCse_o(0)-LCe_o'(0)+RCsE_o(s)-RCe_o(0)+E_o(s)=E_i(s)$$

Agrupando los términos que contienen $E_o(s)$:

$$E_o(s)[LCs^2+RCs+1]=E_i(s)+LCse_o(0)+LCe_o'(0)+RCe_o(0)$$

Despejando $E_o(s)$:

$$E_o(s)=\frac{E_i(s)+LCse_o(0)+LCe_o'(0)+RCe_o(0)}{LCs^2+RCs+1}$$

Esta expresión representa el comportamiento del sistema considerando condiciones iniciales generales.

---

# 9. Condiciones Iniciales Cero

Para obtener la función de transferencia se consideran condiciones iniciales cero:

$$e_o(0)=0$$

$$e_o'(0)=0$$

Entonces la ecuación anterior queda:

$$E_o(s)[LCs^2+RCs+1]=E_i(s)$$

Despejando:

$$E_o(s)=\frac{E_i(s)}{LCs^2+RCs+1}$$

Por lo tanto, la función de transferencia es:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

Esta función de transferencia representa la relación entre el voltaje de salida y el voltaje de entrada del circuito.

---

# 10. Forma Normalizada de la Función de Transferencia

La función de transferencia es:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

Dividiendo el numerador y el denominador entre $LC$:

$$\frac{E_o(s)}{E_i(s)}=\frac{\frac{1}{LC}}{s^2+\frac{R}{L}s+\frac{1}{LC}}$$

La forma estándar de un sistema de segundo orden es:

$$\frac{E_o(s)}{E_i(s)}=\frac{\omega_n^2}{s^2+2\zeta\omega_ns+\omega_n^2}$$

Comparando ambas expresiones:

$$\omega_n^2=\frac{1}{LC}$$

Por lo tanto:

$$\boxed{\omega_n=\frac{1}{\sqrt{LC}}}$$

Además:

$$2\zeta\omega_n=\frac{R}{L}$$

De esta relación se obtiene:

$$\boxed{\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}}$$

---

# 11. Ecuación Característica

La ecuación característica se obtiene igualando a cero el denominador de la función de transferencia:

$$LCs^2+RCs+1=0$$

Dividiendo entre $LC$:

$$\boxed{s^2+\frac{R}{L}s+\frac{1}{LC}=0}$$

Las raíces de esta ecuación representan los polos del sistema.

Los polos permiten determinar el comportamiento dinámico del circuito.

---

# 12. Frecuencia Natural y Amortiguamiento

La frecuencia natural no amortiguada es:

$$\boxed{\omega_n=\frac{1}{\sqrt{LC}}}$$

El factor de amortiguamiento es:

$$\boxed{\alpha=\frac{R}{2L}}$$

El factor de amortiguamiento relativo es:

$$\boxed{\zeta=\frac{\alpha}{\omega_n}}$$

También puede escribirse como:

$$\boxed{\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}}$$

Para un sistema subamortiguado, la frecuencia amortiguada es:

$$\boxed{\omega_d=\sqrt{\omega_n^2-\alpha^2}}$$

---

# 13. Clasificación del Sistema

El comportamiento del circuito depende de la relación entre el factor de amortiguamiento $\alpha$ y la frecuencia natural $\omega_n$.

## Sistema Subamortiguado

El sistema es subamortiguado cuando:

$$\alpha<\omega_n$$

Equivalentemente:

$$R<2\sqrt{\frac{L}{C}}$$

Los polos son complejos conjugados:

$$s_{1,2}=-\alpha\pm j\omega_d$$

La frecuencia amortiguada es:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

En este caso, el circuito presenta oscilaciones que disminuyen progresivamente con el tiempo.

---

## Sistema Críticamente Amortiguado

El sistema es críticamente amortiguado cuando:

$$\alpha=\omega_n$$

Equivalentemente:

$$R=2\sqrt{\frac{L}{C}}$$

El sistema presenta un polo real repetido:

$$s_1=s_2=-\alpha$$

La respuesta regresa al equilibrio sin presentar oscilaciones.

---

## Sistema Sobreamortiguado

El sistema es sobreamortiguado cuando:

$$\alpha>\omega_n$$

Equivalentemente:

$$R>2\sqrt{\frac{L}{C}}$$

Los polos son reales y diferentes:

$$s_{1,2}=-\alpha\pm\sqrt{\alpha^2-\omega_n^2}$$

La respuesta no presenta oscilaciones.

---

# 14. Entrada Escalón

Una entrada escalón de amplitud $E_0$ puede representarse como:

$$e_i(t)=E_0u(t)$$

La transformada de Laplace de esta entrada es:

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

El término:

$$e^{-\alpha t}$$

representa el decaimiento de la respuesta debido al amortiguamiento.

Los términos:

$$\cos(\omega_dt)$$

y:

$$\sin(\omega_dt)$$

representan el comportamiento oscilatorio del sistema.

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

Para una entrada escalón de amplitud $E_0$, el voltaje de salida alcanza finalmente el valor:

$$e_o(\infty)=E_0$$

La carga almacenada en el capacitor está dada por:

$$q(t)=Ce_o(t)$$

Por lo tanto, la carga final es:

$$q(\infty)=CE_0$$

La corriente final es:

$$i(\infty)=0$$

El resultado muestra que el capacitor termina cargándose hasta alcanzar el voltaje de entrada.

---

# 18. Interpretación Física

El comportamiento del circuito RLC se debe al intercambio de energía entre el inductor y el capacitor.

El capacitor almacena energía en forma de campo eléctrico.

El inductor almacena energía en forma de campo magnético.

La resistencia disipa energía en forma de calor.

Cuando el circuito es subamortiguado, la energía se intercambia entre el inductor y el capacitor y se producen oscilaciones.

La resistencia provoca que estas oscilaciones disminuyan progresivamente.

Por esta razón, la resistencia tiene una influencia directa sobre el amortiguamiento del sistema.

---

# 19. Resumen del Modelo Matemático

La ecuación diferencial del sistema es:

$$\boxed{LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)}$$

La ecuación diferencial normalizada es:

$$\boxed{\frac{d^2e_o(t)}{dt^2}+\frac{R}{L}\frac{de_o(t)}{dt}+\frac{1}{LC}e_o(t)=\frac{1}{LC}e_i(t)}$$

La ecuación característica es:

$$\boxed{LCs^2+RCs+1=0}$$

La frecuencia natural es:

$$\boxed{\omega_n=\frac{1}{\sqrt{LC}}}$$

El factor de amortiguamiento es:

$$\boxed{\alpha=\frac{R}{2L}}$$

El factor de amortiguamiento relativo es:

$$\boxed{\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}}$$

La frecuencia amortiguada es:

$$\boxed{\omega_d=\sqrt{\omega_n^2-\alpha^2}}$$

La función de transferencia es:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

---

# 20. Programa en Python

El programa desarrollado en Python permite realizar automáticamente el análisis matemático del circuito RLC.

El usuario puede introducir los parámetros del circuito y las condiciones iniciales.

El programa permite calcular:

1. La ecuación diferencial.
2. La ecuación diferencial normalizada.
3. La ecuación característica.
4. La función de transferencia.
5. La frecuencia natural $\omega_n$.
6. El factor de amortiguamiento $\alpha$.
7. El factor de amortiguamiento relativo $\zeta$.
8. La frecuencia amortiguada $\omega_d$.
9. Los polos del sistema.
10. El tipo de respuesta.
11. La transformada de Laplace de la entrada.
12. La transformada de Laplace de la salida.
13. La respuesta temporal $e_o(t)$.
14. La corriente $i(t)$.
15. La carga $q(t)$.
16. Las gráficas del sistema.

---

# 21. Ejecución del Programa

Primero se deben instalar las dependencias necesarias:

```bash
pip install -r requirements.txt
```

Después se ejecuta el programa:

```bash
python main.py
```

El programa solicitará los parámetros correspondientes al circuito RLC y realizará automáticamente los cálculos.

---

# 22. Tecnologías Utilizadas

- Python
- NumPy
- SymPy
- Matplotlib

---

# 23. Conclusión

El circuito RLC en serie puede modelarse como un sistema dinámico de segundo orden.

A partir de las relaciones eléctricas de sus componentes y de la Ley de Kirchhoff de Voltajes se obtiene la ecuación diferencial:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Esta ecuación relaciona directamente el voltaje de entrada $e_i(t)$ con el voltaje de salida $e_o(t)$.

Posteriormente, mediante la transformada de Laplace y considerando condiciones iniciales cero:

$$LCs^2E_o(s)+RCsE_o(s)+E_o(s)=E_i(s)$$

Despejando la relación entre la salida y la entrada:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

Esta función de transferencia permite analizar el comportamiento dinámico del circuito en el dominio de Laplace.

Además, mediante los parámetros $\omega_n$, $\alpha$ y $\zeta$ es posible determinar si el sistema es subamortiguado, críticamente amortiguado o sobreamortiguado.

El análisis demuestra cómo un circuito eléctrico puede representarse mediante un modelo matemático de sistemas de control y cómo la transformada de Laplace permite estudiar su comportamiento de una manera algebraica.
