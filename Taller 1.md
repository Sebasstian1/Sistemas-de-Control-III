# Análisis de un Circuito RLC en Serie

## Introducción

Un circuito RLC en serie es un sistema eléctrico formado por una resistencia $R$, una inductancia $L$ y un capacitor $C$ conectados en serie.

Este tipo de circuito es importante en el estudio de sistemas de control porque su comportamiento puede describirse mediante una ecuación diferencial de segundo orden. Esto permite analizar conceptos como polos, estabilidad, amortiguamiento, frecuencia natural y respuesta transitoria.

En este proyecto se obtiene el modelo matemático del circuito RLC a partir de la Ley de Kirchhoff de Voltajes. Posteriormente, se aplica la transformada de Laplace para obtener la función de transferencia entre el voltaje de entrada y el voltaje de salida.

Para el análisis se utilizan las siguientes variables:

- $e_i(t)$: voltaje de entrada del circuito.
- $e_o(t)$: voltaje de salida del circuito.
- $R$: resistencia.
- $L$: inductancia.
- $C$: capacitancia.
- $i(t)$: corriente que circula por el circuito.
- $q(t)$: carga eléctrica almacenada en el capacitor.
- $E_i(s)$: transformada de Laplace de $e_i(t)$.
- $E_o(s)$: transformada de Laplace de $e_o(t)$.

---

# 1. Circuito RLC en Serie

El circuito RLC en serie está formado por tres elementos eléctricos:

- Una resistencia $R$.
- Una inductancia $L$.
- Un capacitor $C$.

Los tres elementos se encuentran conectados en serie, por lo que la misma corriente $i(t)$ circula por todos ellos.

El voltaje de entrada del sistema se representa mediante $e_i(t)$.

Para este análisis, el voltaje de salida $e_o(t)$ se considera como el voltaje presente en el capacitor.

Por lo tanto:

$$e_o(t)=\frac{q(t)}{C}$$

El objetivo principal es encontrar una relación matemática entre la entrada $e_i(t)$ y la salida $e_o(t)$.

---

# 2. Elementos del Circuito

## 2.1 Resistencia

La resistencia es el elemento encargado de oponerse al paso de la corriente eléctrica y disipar energía en forma de calor.

De acuerdo con la Ley de Ohm, el voltaje asociado a la resistencia depende de la corriente que circula por ella.

$$e_R(t)=Ri(t)$$

En el modelo matemático, la resistencia es la responsable del amortiguamiento del sistema.

Un valor mayor de $R$ produce un mayor amortiguamiento y reduce las oscilaciones del circuito.

---

## 2.2 Inductor

El inductor almacena energía en forma de campo magnético.

El voltaje de un inductor depende de la variación de la corriente con respecto al tiempo.

$$e_L(t)=L\frac{di(t)}{dt}$$

donde $L$ representa la inductancia medida en henrios.

La presencia del término $\frac{di(t)}{dt}$ hace que el inductor contribuya al comportamiento dinámico del sistema.

---

## 2.3 Capacitor

El capacitor almacena energía en forma de campo eléctrico.

El voltaje del capacitor está relacionado con la carga eléctrica mediante:

$$e_o(t)=\frac{q(t)}{C}$$

donde $C$ representa la capacitancia.

La corriente que circula por el capacitor está relacionada con la variación de la carga:

$$i(t)=\frac{dq(t)}{dt}$$

Como:

$$q(t)=Ce_o(t)$$

podemos derivar ambos lados:

$$\frac{dq(t)}{dt}=C\frac{de_o(t)}{dt}$$

Por lo tanto:

$$i(t)=C\frac{de_o(t)}{dt}$$

Esta relación será utilizada para obtener la ecuación diferencial del sistema únicamente en función de la entrada y la salida.

---

# 3. Ley de Kirchhoff de Voltajes

Para obtener el modelo matemático del circuito se utiliza la Ley de Kirchhoff de Voltajes.

Esta ley establece que la suma de las caídas de voltaje alrededor de una malla debe ser igual al voltaje suministrado por la fuente.

Para el circuito RLC:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Esta ecuación contiene la resistencia, el inductor y el capacitor.

Sin embargo, todavía aparece la corriente $i(t)$, mientras que nuestro objetivo es obtener una ecuación que relacione directamente la entrada $e_i(t)$ con la salida $e_o(t)$.

Para lograrlo, utilizamos la relación del capacitor.

---

# 4. Obtención de la Ecuación Diferencial

Sabemos que:

$$i(t)=C\frac{de_o(t)}{dt}$$

Derivando esta expresión:

$$\frac{di(t)}{dt}=C\frac{d^2e_o(t)}{dt^2}$$

Ahora sustituimos estas dos expresiones en la ecuación de Kirchhoff:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Sustituyendo la corriente:

$$e_i(t)=RC\frac{de_o(t)}{dt}+LC\frac{d^2e_o(t)}{dt^2}+e_o(t)$$

Reordenando los términos:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Por lo tanto, la ecuación diferencial del sistema es:

$$\boxed{LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)}$$

Esta es una ecuación diferencial lineal de segundo orden.

La ecuación muestra cómo el voltaje de entrada $e_i(t)$ determina la evolución temporal del voltaje de salida $e_o(t)$.

---

# 5. Ecuación Diferencial Normalizada

La ecuación obtenida es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Dividiendo toda la ecuación entre $LC$:

$$\frac{d^2e_o(t)}{dt^2}+\frac{R}{L}\frac{de_o(t)}{dt}+\frac{1}{LC}e_o(t)=\frac{1}{LC}e_i(t)$$

Esta forma es útil porque permite comparar el circuito con el modelo estándar de un sistema de segundo orden.

La ecuación característica asociada será:

$$s^2+\frac{R}{L}s+\frac{1}{LC}=0$$

---

# 6. Condiciones Iniciales

Para resolver completamente la ecuación diferencial es necesario conocer las condiciones iniciales del sistema.

El voltaje inicial del capacitor se representa mediante:

$$e_o(0)=e_{o0}$$

La corriente inicial del circuito se representa mediante:

$$i(0)=i_0$$

Como:

$$i(t)=C\frac{de_o(t)}{dt}$$

en el instante inicial se obtiene:

$$i(0)=Ce_o'(0)$$

Por lo tanto:

$$e_o'(0)=\frac{i_0}{C}$$

Las condiciones iniciales pueden expresarse como:

$$e_o(0)=e_{o0}$$

$$e_o'(0)=\frac{i_0}{C}$$

Cuando se estudia la función de transferencia normalmente se consideran condiciones iniciales cero:

$$e_o(0)=0$$

$$e_o'(0)=0$$

---

# 7. Transformada de Laplace

Una vez obtenida la ecuación diferencial, se utiliza la transformada de Laplace para pasar del dominio del tiempo al dominio de la frecuencia compleja $s$.

La ecuación diferencial es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

La transformada de Laplace permite convertir las derivadas en expresiones algebraicas.

Para la primera derivada:

$$\mathcal{L}\left\{\frac{de_o(t)}{dt}\right\}=sE_o(s)-e_o(0)$$

Para la segunda derivada:

$$\mathcal{L}\left\{\frac{d^2e_o(t)}{dt^2}\right\}=s^2E_o(s)-se_o(0)-e_o'(0)$$

Además:

$$\mathcal{L}\{e_o(t)\}=E_o(s)$$

y:

$$\mathcal{L}\{e_i(t)\}=E_i(s)$$

---

# 8. Aplicación de la Transformada de Laplace

Aplicando la transformada de Laplace a toda la ecuación diferencial:

$$LC[s^2E_o(s)-se_o(0)-e_o'(0)]+RC[sE_o(s)-e_o(0)]+E_o(s)=E_i(s)$$

Distribuyendo los términos:

$$LCs^2E_o(s)-LCse_o(0)-LCe_o'(0)+RCsE_o(s)-RCe_o(0)+E_o(s)=E_i(s)$$

Agrupando los términos que contienen $E_o(s)$:

$$E_o(s)(LCs^2+RCs+1)=E_i(s)+LCse_o(0)+LCe_o'(0)+RCe_o(0)$$

Por lo tanto:

$$E_o(s)=\frac{E_i(s)+LCse_o(0)+LCe_o'(0)+RCe_o(0)}{LCs^2+RCs+1}$$

Esta expresión representa el circuito considerando condiciones iniciales generales.

---

# 9. Función de Transferencia

Para obtener la función de transferencia se consideran condiciones iniciales cero:

$$e_o(0)=0$$

$$e_o'(0)=0$$

Entonces:

$$E_o(s)(LCs^2+RCs+1)=E_i(s)$$

Despejando:

$$E_o(s)=\frac{E_i(s)}{LCs^2+RCs+1}$$

Por lo tanto, la función de transferencia es:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

Esta función de transferencia describe matemáticamente la relación entre el voltaje de entrada y el voltaje de salida del circuito RLC.

---

# 10. Forma Estándar de Segundo Orden

La función de transferencia obtenida es:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

Dividiendo el denominador entre $LC$:

$$\frac{E_o(s)}{E_i(s)}=\frac{\frac{1}{LC}}{s^2+\frac{R}{L}s+\frac{1}{LC}}$$

La forma estándar de un sistema de segundo orden es:

$$\frac{E_o(s)}{E_i(s)}=\frac{\omega_n^2}{s^2+2\zeta\omega_ns+\omega_n^2}$$

Comparando ambas expresiones:

$$\omega_n^2=\frac{1}{LC}$$

Por lo tanto:

$$\boxed{\omega_n=\frac{1}{\sqrt{LC}}}$$

Además:

$$2\zeta\omega_n=\frac{R}{L}$$

El factor de amortiguamiento relativo es:

$$\boxed{\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}}$$

---

# 11. Ecuación Característica

La ecuación característica se obtiene igualando a cero el denominador de la función de transferencia:

$$LCs^2+RCs+1=0$$

Dividiendo entre $LC$:

$$\boxed{s^2+\frac{R}{L}s+\frac{1}{LC}=0}$$

Esta ecuación permite encontrar los polos del sistema y determinar el tipo de respuesta.

---

# 12. Factor de Amortiguamiento

El factor de amortiguamiento se define como:

$$\boxed{\alpha=\frac{R}{2L}}$$

La relación entre el factor de amortiguamiento y la frecuencia natural es:

$$\zeta=\frac{\alpha}{\omega_n}$$

Por lo tanto:

$$\boxed{\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}}$$

Este parámetro permite determinar si el sistema presenta oscilaciones.

---

# 13. Clasificación del Sistema

El circuito RLC puede presentar tres tipos de respuesta dependiendo del valor del factor de amortiguamiento.

## Sistema Subamortiguado

Se presenta cuando:

$$\alpha<\omega_n$$

Equivalentemente:

$$R<2\sqrt{\frac{L}{C}}$$

Los polos son complejos conjugados:

$$s_{1,2}=-\alpha\pm j\omega_d$$

La frecuencia amortiguada es:

$$\boxed{\omega_d=\sqrt{\omega_n^2-\alpha^2}}$$

En este caso, la respuesta presenta oscilaciones que disminuyen progresivamente debido a la resistencia.

---

## Sistema Críticamente Amortiguado

Se presenta cuando:

$$\alpha=\omega_n$$

Equivalentemente:

$$R=2\sqrt{\frac{L}{C}}$$

El sistema tiene un polo real repetido:

$$s_1=s_2=-\alpha$$

La respuesta regresa al equilibrio sin presentar oscilaciones.

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

Una entrada escalón puede representarse mediante:

$$e_i(t)=E_0u(t)$$

donde $E_0$ representa la amplitud del escalón.

Su transformada de Laplace es:

$$E_i(s)=\frac{E_0}{s}$$

Utilizando la función de transferencia:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

se obtiene:

$$E_o(s)=\frac{E_0}{s(LCs^2+RCs+1)}$$

La respuesta temporal dependerá de los valores de $R$, $L$ y $C$.

---

# 15. Respuesta Temporal Subamortiguada

Para un sistema subamortiguado con condiciones iniciales cero, la respuesta al escalón del voltaje de salida es:

$$e_o(t)=E_0\left[1-e^{-\alpha t}\left(\cos(\omega_dt)+\frac{\alpha}{\omega_d}\sin(\omega_dt)\right)\right]$$

donde:

$$\alpha=\frac{R}{2L}$$

y:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

Esta expresión muestra que el voltaje de salida comienza desde cero, puede presentar oscilaciones y finalmente converge al valor de entrada.

---

# 16. Corriente del Circuito

La corriente está relacionada con el voltaje de salida mediante:

$$i(t)=C\frac{de_o(t)}{dt}$$

Para el caso subamortiguado y una entrada escalón:

$$i(t)=\frac{E_0}{L\omega_d}e^{-\alpha t}\sin(\omega_dt)$$

La corriente presenta una respuesta oscilatoria amortiguada.

A medida que pasa el tiempo:

$$i(t)\rightarrow0$$

Esto ocurre porque, en estado estacionario de corriente continua, el capacitor se comporta como un circuito abierto.

---

# 17. Valor Final

Para una entrada escalón de amplitud $E_0$, el voltaje de salida alcanza finalmente el valor:

$$e_o(\infty)=E_0$$

La carga almacenada en el capacitor es:

$$q(t)=Ce_o(t)$$

Por lo tanto, en estado estacionario:

$$q(\infty)=CE_0$$

La corriente final es:

$$i(\infty)=0$$

---

# 18. Interpretación Física

El comportamiento del circuito RLC se debe al intercambio de energía entre el inductor y el capacitor.

El capacitor almacena energía en forma de campo eléctrico.

El inductor almacena energía en forma de campo magnético.

La resistencia disipa energía en forma de calor.

Cuando el circuito es subamortiguado, la energía se intercambia entre el capacitor y el inductor produciendo oscilaciones. La resistencia provoca que estas oscilaciones disminuyan progresivamente.

Por esta razón, el valor de $R$ tiene una influencia directa sobre el amortiguamiento del sistema.

---

# 19. Resumen del Modelo Matemático

La ecuación diferencial obtenida a partir de la Ley de Kirchhoff es:

$$\boxed{LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)}$$

La ecuación característica es:

$$\boxed{LCs^2+RCs+1=0}$$

La frecuencia natural no amortiguada es:

$$\boxed{\omega_n=\frac{1}{\sqrt{LC}}}$$

El factor de amortiguamiento es:

$$\boxed{\alpha=\frac{R}{2L}}$$

El factor de amortiguamiento relativo es:

$$\boxed{\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}}$$

La función de transferencia es:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

Para el caso subamortiguado, la frecuencia amortiguada es:

$$\boxed{\omega_d=\sqrt{\omega_n^2-\alpha^2}}$$

---

# 20. Programa en Python

El programa desarrollado en Python permite realizar automáticamente el análisis matemático del circuito RLC.

El usuario puede introducir los parámetros del circuito y las condiciones iniciales.

El programa permite calcular:

1. La ecuación diferencial del sistema.
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
13. La respuesta temporal.
14. El voltaje de salida $e_o(t)$.
15. La corriente $i(t)$.
16. La carga $q(t)$.
17. Las gráficas correspondientes.

---

# 21. Ejecución del Programa

Primero se deben instalar las dependencias necesarias:

```bash
pip install -r requirements.txt
```

Después se ejecuta el programa mediante:

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

A partir de la Ley de Kirchhoff y de las relaciones fundamentales de la resistencia, el inductor y el capacitor se obtiene la ecuación diferencial:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Posteriormente, mediante la transformada de Laplace y considerando condiciones iniciales cero, se obtiene:

$$LCs^2E_o(s)+RCsE_o(s)+E_o(s)=E_i(s)$$

Despejando la relación entre la salida y la entrada:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

Esta función de transferencia permite analizar el comportamiento dinámico del circuito en el dominio de Laplace.

Además, mediante los parámetros $\omega_n$, $\alpha$ y $\zeta$ es posible determinar si el circuito es subamortiguado, críticamente amortiguado o sobreamortiguado.

De esta manera, el circuito RLC proporciona un ejemplo práctico de cómo un sistema físico puede transformarse en un modelo matemático y posteriormente analizarse utilizando herramientas de sistemas de control.
