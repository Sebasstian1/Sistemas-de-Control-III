# Sistemas de Control - Circuito RLC en Serie

Este proyecto presenta el análisis matemático de un circuito RLC en serie mediante ecuaciones diferenciales y la transformada de Laplace.

El objetivo es obtener el modelo matemático del circuito a partir de la Ley de Kirchhoff, analizar las condiciones iniciales, obtener la función de transferencia y determinar la respuesta temporal del sistema.

Para el análisis se utilizan las siguientes variables:

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

## 1. Descripción del Sistema

Un circuito RLC en serie está compuesto por una resistencia $R$, una inductancia $L$ y un capacitor $C$ conectados en serie.

Al estar conectados en serie, la misma corriente $i(t)$ circula por los tres elementos.

La señal de entrada es el voltaje $e_i(t)$ y la señal de salida es el voltaje $e_o(t)$.

El circuito RLC representa un sistema dinámico de segundo orden y puede utilizarse como modelo para el estudio de sistemas de control.

---

## 2. Relación entre la Corriente y el Voltaje de Salida

Considerando que el voltaje de salida $e_o(t)$ corresponde al voltaje del capacitor, la carga eléctrica está relacionada con dicho voltaje mediante:

$$q(t)=Ce_o(t)$$

La corriente se obtiene derivando la carga:

$$i(t)=\frac{dq(t)}{dt}$$

Por lo tanto:

$$i(t)=C\frac{de_o(t)}{dt}$$

Derivando nuevamente:

$$\frac{di(t)}{dt}=C\frac{d^2e_o(t)}{dt^2}$$

Estas relaciones permiten expresar la ecuación del circuito únicamente en función de la entrada $e_i(t)$ y la salida $e_o(t)$.

---

## 3. Ley de Kirchhoff

Aplicando la Ley de Kirchhoff de Voltajes al circuito:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Utilizando las relaciones:

$$i(t)=C\frac{de_o(t)}{dt}$$

y:

$$\frac{di(t)}{dt}=C\frac{d^2e_o(t)}{dt^2}$$

Sustituyendo en la ecuación de Kirchhoff:

$$e_i(t)=RC\frac{de_o(t)}{dt}+LC\frac{d^2e_o(t)}{dt^2}+e_o(t)$$

Reordenando los términos:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Esta es la ecuación diferencial de segundo orden que relaciona directamente el voltaje de entrada con el voltaje de salida del circuito RLC.

---

## 4. Ecuación Diferencial Normalizada

Partiendo de:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Dividiendo toda la ecuación entre $LC$:

$$\frac{d^2e_o(t)}{dt^2}+\frac{R}{L}\frac{de_o(t)}{dt}+\frac{1}{LC}e_o(t)=\frac{1}{LC}e_i(t)$$

Esta forma permite comparar directamente el circuito con la forma estándar de un sistema de segundo orden.

---

## 5. Condiciones Iniciales

Las condiciones iniciales del circuito pueden expresarse mediante el voltaje inicial del capacitor y la corriente inicial.

El voltaje inicial de salida es:

$$e_o(0)=e_{o0}$$

La corriente inicial es:

$$i(0)=i_0$$

Como:

$$i(t)=C\frac{de_o(t)}{dt}$$

entonces:

$$\frac{de_o(0)}{dt}=\frac{i_0}{C}$$

Por lo tanto, las condiciones iniciales para la ecuación diferencial de salida son:

$$e_o(0)=e_{o0}$$

y:

$$e_o'(0)=\frac{i_0}{C}$$

---

## 6. Transformada de Laplace

Partimos de la ecuación diferencial:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Las transformadas necesarias son:

$$\mathcal{L}\left\{\frac{de_o(t)}{dt}\right\}=sE_o(s)-e_o(0)$$

$$\mathcal{L}\left\{\frac{d^2e_o(t)}{dt^2}\right\}=s^2E_o(s)-se_o(0)-e_o'(0)$$

Aplicando la transformada de Laplace:

$$LC[s^2E_o(s)-se_o(0)-e_o'(0)]+RC[sE_o(s)-e_o(0)]+E_o(s)=E_i(s)$$

Agrupando los términos que contienen $E_o(s)$:

$$E_o(s)(LCs^2+RCs+1)=E_i(s)+LCse_o(0)+LCe_o'(0)+RCe_o(0)$$

Por lo tanto:

$$E_o(s)=\frac{E_i(s)+LCse_o(0)+LCe_o'(0)+RCe_o(0)}{LCs^2+RCs+1}$$

---

## 7. Condiciones Iniciales Cero

Para condiciones iniciales cero:

$$e_o(0)=0$$

y:

$$e_o'(0)=0$$

la expresión anterior se simplifica a:

$$E_o(s)=\frac{E_i(s)}{LCs^2+RCs+1}$$

Por lo tanto, la función de transferencia entre la entrada y la salida es:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

Esta es la función de transferencia del circuito RLC cuando la salida se toma en el capacitor.

---

## 8. Función de Transferencia en Forma Normalizada

Partiendo de:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

Dividiendo el denominador entre $LC$:

$$\frac{E_o(s)}{E_i(s)}=\frac{\frac{1}{LC}}{s^2+\frac{R}{L}s+\frac{1}{LC}}$$

Esta expresión tiene la forma estándar de un sistema de segundo orden:

$$\frac{E_o(s)}{E_i(s)}=\frac{\omega_n^2}{s^2+2\zeta\omega_ns+\omega_n^2}$$

donde:

$$\omega_n=\frac{1}{\sqrt{LC}}$$

y:

$$2\zeta\omega_n=\frac{R}{L}$$

---

## 9. Ecuación Característica

La ecuación característica se obtiene igualando a cero el denominador de la función de transferencia:

$$LCs^2+RCs+1=0$$

Dividiendo entre $LC$:

$$s^2+\frac{R}{L}s+\frac{1}{LC}=0$$

Esta ecuación permite determinar los polos del sistema.

---

## 10. Parámetros del Sistema

La frecuencia natural no amortiguada es:

$$\omega_n=\frac{1}{\sqrt{LC}}$$

El factor de amortiguamiento es:

$$\alpha=\frac{R}{2L}$$

El factor de amortiguamiento relativo es:

$$\zeta=\frac{\alpha}{\omega_n}$$

Por lo tanto:

$$\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}$$

Cuando el sistema es subamortiguado, la frecuencia amortiguada es:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

También puede expresarse como:

$$\omega_d=\sqrt{\frac{1}{LC}-\frac{R^2}{4L^2}}$$

---

## 11. Tipos de Respuesta

El comportamiento del circuito depende de los valores de $R$, $L$ y $C$.

### Sistema Subamortiguado

Se presenta cuando:

$$\alpha<\omega_n$$

Equivalentemente:

$$R<2\sqrt{\frac{L}{C}}$$

Los polos son complejos conjugados:

$$s_{1,2}=-\alpha\pm j\omega_d$$

La respuesta presenta oscilaciones amortiguadas.

---

### Sistema Críticamente Amortiguado

Se presenta cuando:

$$\alpha=\omega_n$$

Equivalentemente:

$$R=2\sqrt{\frac{L}{C}}$$

El sistema posee un polo real repetido:

$$s_1=s_2=-\alpha$$

La respuesta no presenta oscilaciones.

---

### Sistema Sobreamortiguado

Se presenta cuando:

$$\alpha>\omega_n$$

Equivalentemente:

$$R>2\sqrt{\frac{L}{C}}$$

El sistema posee dos polos reales diferentes:

$$s_{1,2}=-\alpha\pm\sqrt{\alpha^2-\omega_n^2}$$

La respuesta no presenta oscilaciones.

---

# 12. Entrada Escalón

Para una entrada escalón de amplitud $E_0$:

$$e_i(t)=E_0u(t)$$

Su transformada de Laplace es:

$$E_i(s)=\frac{E_0}{s}$$

Utilizando la función de transferencia:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

se obtiene:

$$E_o(s)=\frac{E_0}{s(LCs^2+RCs+1)}$$

La respuesta temporal depende de los valores de $R$, $L$ y $C$.

---

## 13. Respuesta Temporal Subamortiguada

Para condiciones iniciales cero y una entrada escalón, si el sistema es subamortiguado, la respuesta del voltaje de salida es:

$$e_o(t)=E_0\left[1-e^{-\alpha t}\left(\cos(\omega_dt)+\frac{\alpha}{\omega_d}\sin(\omega_dt)\right)\right]$$

donde:

$$\alpha=\frac{R}{2L}$$

y:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

La carga del capacitor es:

$$q(t)=Ce_o(t)$$

Por lo tanto:

$$q(t)=CE_0\left[1-e^{-\alpha t}\left(\cos(\omega_dt)+\frac{\alpha}{\omega_d}\sin(\omega_dt)\right)\right]$$

---

## 14. Corriente del Circuito

La corriente está relacionada con el voltaje de salida mediante:

$$i(t)=C\frac{de_o(t)}{dt}$$

Para el caso subamortiguado con condiciones iniciales cero y entrada escalón:

$$i(t)=\frac{E_0}{L\omega_d}e^{-\alpha t}\sin(\omega_dt)$$

donde:

$$\alpha=\frac{R}{2L}$$

y:

$$\omega_d=\sqrt{\frac{1}{LC}-\frac{R^2}{4L^2}}$$

La corriente tiende a cero cuando:

$$t\rightarrow\infty$$

---

## 15. Valor Final

Para una entrada escalón de amplitud $E_0$, el valor final del voltaje de salida es:

$$e_o(\infty)=E_0$$

La carga final del capacitor es:

$$q(\infty)=CE_0$$

La corriente final es:

$$i(\infty)=0$$

Esto corresponde al comportamiento esperado de un capacitor en estado estacionario de corriente continua.

---

## 16. Interpretación Física

El circuito RLC intercambia energía entre el inductor y el capacitor.

El inductor almacena energía en forma de campo magnético, mientras que el capacitor almacena energía en forma de campo eléctrico.

La resistencia disipa energía en forma de calor.

La resistencia determina el nivel de amortiguamiento del sistema.

Los valores de $R$, $L$ y $C$ determinan si el sistema es subamortiguado, críticamente amortiguado o sobreamortiguado.

El factor de amortiguamiento relativo está dado por:

$$\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}$$

Por lo tanto:

- Si $0<\zeta<1$, el sistema es subamortiguado.
- Si $\zeta=1$, el sistema es críticamente amortiguado.
- Si $\zeta>1$, el sistema es sobreamortiguado.

---

# 17. Programa en Python

El programa desarrollado en Python permite realizar automáticamente el análisis matemático del circuito RLC.

El usuario puede introducir:

- Resistencia $R$.
- Inductancia $L$.
- Capacitancia $C$.
- Voltaje de entrada $e_i(t)$.
- Voltaje inicial de salida $e_o(0)$.
- Corriente inicial $i(0)$.
- Tiempo de simulación.

El programa calcula:

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
11. $E_i(s)$.
12. $E_o(s)$.
13. La respuesta temporal $e_o(t)$.
14. La carga $q(t)$.
15. La corriente $i(t)$.
16. Las gráficas correspondientes.

---

# 18. Ejecución

Primero instalar las dependencias:

```bash
pip install -r requirements.txt
```

Después ejecutar el programa:

```bash
python main.py
```

El programa solicitará los parámetros del circuito y mostrará los resultados correspondientes.

---

# 19. Tecnologías Utilizadas

- Python
- NumPy
- SymPy
- Matplotlib

---

# 20. Conclusión

El circuito RLC en serie puede modelarse mediante la siguiente ecuación diferencial:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Esta ecuación relaciona directamente el voltaje de entrada $e_i(t)$ con el voltaje de salida $e_o(t)$.

Aplicando la transformada de Laplace y considerando condiciones iniciales cero:

$$LCs^2E_o(s)+RCsE_o(s)+E_o(s)=E_i(s)$$

Por lo tanto, la función de transferencia del circuito es:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

La frecuencia natural no amortiguada es:

$$\omega_n=\frac{1}{\sqrt{LC}}$$

El factor de amortiguamiento es:

$$\alpha=\frac{R}{2L}$$

y el factor de amortiguamiento relativo es:

$$\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}$$

La clasificación del sistema depende de la relación entre $\alpha$ y $\omega_n$.

Si el sistema es subamortiguado:

$$\alpha<\omega_n$$

la frecuencia amortiguada es:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

y para una entrada escalón de amplitud $E_0$, la respuesta del voltaje de salida es:

$$e_o(t)=E_0\left[1-e^{-\alpha t}\left(\cos(\omega_dt)+\frac{\alpha}{\omega_d}\sin(\omega_dt)\right)\right]$$

La corriente correspondiente es:

$$i(t)=\frac{E_0}{L\omega_d}e^{-\alpha t}\sin(\omega_dt)$$

De esta manera, el modelo permite analizar el comportamiento dinámico del circuito RLC utilizando únicamente las variables de entrada y salida del sistema, sin asumir valores numéricos específicos para $R$, $L$ y $C$.
