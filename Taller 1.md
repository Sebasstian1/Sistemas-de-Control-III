# Sistemas de Control - Circuito RLC en Serie

Este proyecto presenta el análisis matemático de un circuito RLC en serie mediante ecuaciones diferenciales y la transformada de Laplace.

El objetivo es obtener el modelo matemático del circuito a partir de la Ley de Kirchhoff, analizar las condiciones iniciales, obtener la función de transferencia y determinar la respuesta temporal del sistema.

En este análisis se utilizan:

- $e_i(t)$: voltaje de entrada en el dominio del tiempo.
- $e_o(t)$: voltaje de salida en el dominio del tiempo.
- $E_i(s)$: voltaje de entrada en el dominio de Laplace.
- $E_o(s)$: voltaje de salida en el dominio de Laplace.
- $R$: resistencia.
- $L$: inductancia.
- $C$: capacitancia.
- $q(t)$: carga eléctrica.
- $i(t)$: corriente del circuito.
- $Q(s)$: transformada de Laplace de la carga.
- $I(s)$: transformada de Laplace de la corriente.

---

## 1. Descripción del Sistema

Un circuito RLC en serie está compuesto por una resistencia $R$, una inductancia $L$ y un capacitor $C$ conectados en serie.

Al estar conectados en serie, la misma corriente $i(t)$ circula por los tres elementos.

La señal de entrada del sistema se representa mediante $e_i(t)$ y la señal de salida mediante $e_o(t)$.

El circuito RLC es un sistema eléctrico de segundo orden y puede utilizarse como modelo para el estudio de sistemas dinámicos y sistemas de control.

---

## 2. Elementos del Circuito

### Resistencia

La resistencia disipa energía en forma de calor.

Su voltaje está dado por:

$$e_R(t)=Ri(t)$$

### Inductor

El inductor almacena energía en forma de campo magnético.

Su voltaje está dado por:

$$e_L(t)=L\frac{di(t)}{dt}$$

### Capacitor

El capacitor almacena energía en forma de campo eléctrico.

Su voltaje está dado por:

$$e_C(t)=\frac{q(t)}{C}$$

donde $q(t)$ representa la carga eléctrica.

Además, la corriente y la carga están relacionadas mediante:

$$i(t)=\frac{dq(t)}{dt}$$

---

## 3. Ley de Kirchhoff

Aplicando la Ley de Kirchhoff de Voltajes al circuito:

$$e_i(t)=e_R(t)+e_L(t)+e_C(t)$$

Sustituyendo las expresiones de cada elemento:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+\frac{q(t)}{C}$$

Como:

$$i(t)=\frac{dq(t)}{dt}$$

entonces:

$$\frac{di(t)}{dt}=\frac{d^2q(t)}{dt^2}$$

Por lo tanto:

$$e_i(t)=R\frac{dq(t)}{dt}+L\frac{d^2q(t)}{dt^2}+\frac{q(t)}{C}$$

Finalmente, la ecuación diferencial del circuito es:

$$L\frac{d^2q(t)}{dt^2}+R\frac{dq(t)}{dt}+\frac{1}{C}q(t)=e_i(t)$$

Esta es la ecuación diferencial de segundo orden que describe el comportamiento del circuito RLC.

---

## 4. Ecuación Diferencial en Función de la Corriente

Partiendo de:

$$L\frac{d^2q(t)}{dt^2}+R\frac{dq(t)}{dt}+\frac{1}{C}q(t)=e_i(t)$$

y utilizando:

$$i(t)=\frac{dq(t)}{dt}$$

derivamos ambos lados de la ecuación:

$$L\frac{d^2i(t)}{dt^2}+R\frac{di(t)}{dt}+\frac{1}{C}i(t)=\frac{de_i(t)}{dt}$$

Por lo tanto, la ecuación diferencial en función de la corriente es:

$$L\frac{d^2i(t)}{dt^2}+R\frac{di(t)}{dt}+\frac{1}{C}i(t)=\frac{de_i(t)}{dt}$$

---

## 5. Condiciones Iniciales

Las condiciones iniciales del circuito se representan mediante la carga inicial y la corriente inicial:

$$q(0)=q_0$$

$$i(0)=i_0$$

El voltaje inicial del capacitor está relacionado con la carga mediante:

$$q_0=Ce_C(0)$$

Por lo tanto:

$$q(0)=Ce_C(0)$$

Estas condiciones iniciales permiten determinar la respuesta completa del circuito.

---

## 6. Transformada de Laplace

Partimos de la ecuación diferencial:

$$Lq''(t)+Rq'(t)+\frac{1}{C}q(t)=e_i(t)$$

Las transformadas necesarias son:

$$\mathcal{L}\{q''(t)\}=s^2Q(s)-sq(0)-q'(0)$$

$$\mathcal{L}\{q'(t)\}=sQ(s)-q(0)$$

Aplicando la transformada de Laplace:

$$L[s^2Q(s)-sq(0)-q'(0)]+R[sQ(s)-q(0)]+\frac{1}{C}Q(s)=E_i(s)$$

Agrupando los términos que contienen $Q(s)$:

$$Q(s)\left(Ls^2+Rs+\frac{1}{C}\right)=E_i(s)+Lsq(0)+Lq'(0)+Rq(0)$$

Por lo tanto:

$$Q(s)=\frac{E_i(s)+Lsq(0)+Lq'(0)+Rq(0)}{Ls^2+Rs+\frac{1}{C}}$$

---

## 7. Condiciones Iniciales Cero

Para condiciones iniciales cero:

$$q(0)=0$$

$$i(0)=q'(0)=0$$

la expresión anterior se simplifica a:

$$Q(s)=\frac{E_i(s)}{Ls^2+Rs+\frac{1}{C}}$$

Como:

$$I(s)=sQ(s)$$

se obtiene:

$$I(s)=\frac{sE_i(s)}{Ls^2+Rs+\frac{1}{C}}$$

Por lo tanto, la función de transferencia entre la entrada $e_i(t)$ y la corriente $i(t)$ es:

$$\frac{I(s)}{E_i(s)}=\frac{s}{Ls^2+Rs+\frac{1}{C}}$$

---

## 8. Voltaje de Salida

Si el voltaje de salida $e_o(t)$ corresponde al voltaje del capacitor, entonces:

$$e_o(t)=e_C(t)=\frac{q(t)}{C}$$

Aplicando la transformada de Laplace:

$$E_o(s)=\frac{Q(s)}{C}$$

Para condiciones iniciales cero:

$$Q(s)=\frac{E_i(s)}{Ls^2+Rs+\frac{1}{C}}$$

Por lo tanto:

$$E_o(s)=\frac{E_i(s)}{C\left(Ls^2+Rs+\frac{1}{C}\right)}$$

Simplificando:

$$E_o(s)=\frac{E_i(s)}{LCs^2+RCs+1}$$

Por lo tanto, la función de transferencia entre el voltaje de entrada y el voltaje de salida es:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

Esta es la función de transferencia del circuito cuando la salida $e_o(t)$ se toma sobre el capacitor.

---

## 9. Ecuación Característica

La ecuación característica se obtiene a partir del denominador de la función de transferencia:

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

Para un sistema subamortiguado, la frecuencia amortiguada es:

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

La respuesta natural de la carga tiene la forma:

$$q_n(t)=e^{-\alpha t}[A\cos(\omega_dt)+B\sin(\omega_dt)]$$

La respuesta presenta oscilaciones amortiguadas.

---

### Sistema Críticamente Amortiguado

Se presenta cuando:

$$\alpha=\omega_n$$

Equivalentemente:

$$R=2\sqrt{\frac{L}{C}}$$

El sistema posee un polo real repetido:

$$s_1=s_2=-\alpha$$

La respuesta natural tiene la forma:

$$q_n(t)=(A+Bt)e^{-\alpha t}$$

El sistema regresa al equilibrio sin presentar oscilaciones.

---

### Sistema Sobreamortiguado

Se presenta cuando:

$$\alpha>\omega_n$$

Equivalentemente:

$$R>2\sqrt{\frac{L}{C}}$$

El sistema posee dos polos reales diferentes:

$$s_{1,2}=-\alpha\pm\sqrt{\alpha^2-\omega_n^2}$$

La respuesta natural tiene la forma:

$$q_n(t)=Ae^{s_1t}+Be^{s_2t}$$

El sistema no presenta oscilaciones.

---

# 12. Entrada Escalón

Para una entrada escalón de amplitud $E_0$:

$$e_i(t)=E_0u(t)$$

su transformada de Laplace es:

$$E_i(s)=\frac{E_0}{s}$$

Utilizando la función de transferencia del voltaje de salida:

$$\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

se obtiene:

$$E_o(s)=\frac{E_0}{s(LCs^2+RCs+1)}$$

La respuesta temporal dependerá de los valores de $R$, $L$ y $C$.

---

## 13. Respuesta Temporal para el Caso Subamortiguado

Para condiciones iniciales cero y una entrada escalón, la respuesta del voltaje del capacitor es:

$$e_o(t)=E_0\left[1-e^{-\alpha t}\left(\cos(\omega_dt)+\frac{\alpha}{\omega_d}\sin(\omega_dt)\right)\right]$$

donde:

$$\alpha=\frac{R}{2L}$$

y:

$$\omega_d=\sqrt{\omega_n^2-\alpha^2}$$

La carga del capacitor se obtiene mediante:

$$q(t)=Ce_o(t)$$

Por lo tanto:

$$q(t)=CE_0\left[1-e^{-\alpha t}\left(\cos(\omega_dt)+\frac{\alpha}{\omega_d}\sin(\omega_dt)\right)\right]$$

---

## 14. Corriente del Circuito

La corriente está relacionada con la carga mediante:

$$i(t)=\frac{dq(t)}{dt}$$

Como:

$$q(t)=Ce_o(t)$$

entonces:

$$i(t)=C\frac{de_o(t)}{dt}$$

Para una respuesta subamortiguada con condiciones iniciales cero y entrada escalón:

$$i(t)=\frac{E_0}{L\omega_d}e^{-\alpha t}\sin(\omega_dt)$$

donde:

$$\alpha=\frac{R}{2L}$$

y:

$$\omega_d=\sqrt{\frac{1}{LC}-\frac{R^2}{4L^2}}$$

La corriente presenta una respuesta oscilatoria amortiguada y tiende a cero cuando:

$$t\rightarrow\infty$$

---

## 15. Valor Final

Para una entrada escalón de amplitud $E_0$, el valor final del voltaje del capacitor es:

$$e_o(\infty)=E_0$$

La carga final del capacitor es:

$$q(\infty)=CE_0$$

La corriente final es:

$$i(\infty)=0$$

Esto ocurre porque en estado estacionario de corriente continua el capacitor se comporta como un circuito abierto.

---

## 16. Interpretación Física

El circuito RLC intercambia energía entre el inductor y el capacitor.

El inductor almacena energía en forma de campo magnético, mientras que el capacitor almacena energía en forma de campo eléctrico.

La resistencia disipa energía en forma de calor.

Dependiendo de los valores de $R$, $L$ y $C$, la respuesta puede presentar oscilaciones amortiguadas, una respuesta críticamente amortiguada o una respuesta sobreamortiguada.

La clasificación del sistema se determina mediante:

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
- Voltaje inicial del capacitor.
- Corriente inicial.
- Tiempo de simulación.

El programa calcula:

1. La ecuación diferencial.
2. La ecuación característica.
3. La función de transferencia.
4. La frecuencia natural $\omega_n$.
5. El factor de amortiguamiento $\alpha$.
6. El factor de amortiguamiento relativo $\zeta$.
7. La frecuencia amortiguada $\omega_d$.
8. Los polos del sistema.
9. El tipo de respuesta.
10. $Q(s)$.
11. $I(s)$.
12. $E_i(s)$.
13. $E_o(s)$.
14. La solución temporal $e_o(t)$.
15. La carga $q(t)$.
16. La corriente $i(t)$.
17. Las gráficas correspondientes.

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

El circuito RLC en serie puede modelarse mediante una ecuación diferencial lineal de segundo orden:

$$L\frac{d^2q(t)}{dt^2}+R\frac{dq(t)}{dt}+\frac{1}{C}q(t)=e_i(t)$$

Cuando la salida se toma sobre el capacitor:

$$e_o(t)=\frac{q(t)}{C}$$

Después de aplicar la transformada de Laplace, la relación entre la entrada y la salida es:

$$\boxed{\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}}$$

La ecuación característica del sistema es:

$$LCs^2+RCs+1=0$$

La frecuencia natural no amortiguada es:

$$\omega_n=\frac{1}{\sqrt{LC}}$$

El factor de amortiguamiento es:

$$\alpha=\frac{R}{2L}$$

y el factor de amortiguamiento relativo es:

$$\zeta=\frac{R}{2}\sqrt{\frac{C}{L}}$$

La clasificación del sistema depende de los valores de $R$, $L$ y $C$.

Para un sistema subamortiguado y una entrada escalón de amplitud $E_0$, la respuesta del voltaje de salida es:

$$e_o(t)=E_0\left[1-e^{-\alpha t}\left(\cos(\omega_dt)+\frac{\alpha}{\omega_d}\sin(\omega_dt)\right)\right]$$

y la corriente es:

$$i(t)=\frac{E_0}{L\omega_d}e^{-\alpha t}\sin(\omega_dt)$$

De esta manera, el modelo permite estudiar el comportamiento dinámico del circuito RLC sin asumir valores numéricos específicos para sus componentes.
