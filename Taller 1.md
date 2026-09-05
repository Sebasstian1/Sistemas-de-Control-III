# Sistemas de Control - Circuito RLC en Serie

Este proyecto presenta el análisis matemático de un circuito RLC en serie utilizando ecuaciones diferenciales y la transformada de Laplace.

El objetivo es obtener el modelo matemático del circuito a partir de la Ley de Kirchhoff, analizar sus condiciones iniciales, determinar el tipo de respuesta del sistema y obtener su solución temporal.

---

## 1. Descripción del Sistema

Un circuito RLC en serie está compuesto por:

- Una resistencia de valor $R$.
- Una inductancia de valor $L$.
- Un capacitor de capacitancia $C$.
- Una fuente de voltaje $V(t)$.

Los tres elementos se encuentran conectados en serie, por lo que la misma corriente $i(t)$ circula por la resistencia, el inductor y el capacitor.

El circuito RLC representa un sistema eléctrico de segundo orden y puede utilizarse como modelo para el estudio de sistemas dinámicos.

---

## 2. Elementos del Circuito

### Resistencia

La resistencia disipa energía en forma de calor.

Su voltaje está dado por:

$$
V_R(t) = R i(t)
$$

### Inductor

El inductor almacena energía en forma de campo magnético.

Su voltaje es:

$$
V_L(t) = L \frac{di(t)}{dt}
$$

### Capacitor

El capacitor almacena energía en forma de campo eléctrico.

Su voltaje es:

$$
V_C(t) = \frac{q(t)}{C}
$$

donde $q(t)$ representa la carga eléctrica.

Además:

$$
i(t) = \frac{dq(t)}{dt}
$$

---

## 3. Ley de Kirchhoff

Aplicando la Ley de Kirchhoff de Voltajes:

$$V(t) = V_R(t) + V_L(t) + V_C(t)$$

Sustituyendo las expresiones de cada elemento:

$$V(t) = R i(t) + L \frac{di(t)}{dt} + \frac{q(t)}{C}$$

Como:

$$i(t) = \frac{dq(t)}{dt}$$

entonces:

$$\frac{di(t)}{dt} = \frac{d^2q(t)}{dt^2}$$

Por lo tanto:

$$V(t) = R \frac{dq(t)}{dt} + L \frac{d^2q(t)}{dt^2} + \frac{q(t)}{C}$$

Finalmente:

$$L \frac{d^2q(t)}{dt^2} + R \frac{dq(t)}{dt} + \frac{1}{C}q(t) = V(t)$$

Esta es la ecuación diferencial de segundo orden del circuito RLC.


## 4. Ecuación Diferencial en Función de la Corriente

Partiendo de:

$$
L \frac{d^2q(t)}{dt^2}
+
R \frac{dq(t)}{dt}
+
\frac{1}{C}q(t)
=
V(t)
$$

y utilizando:

$$
i(t) = \frac{dq(t)}{dt}
$$

derivamos ambos lados:

$$
L \frac{d^2i(t)}{dt^2}
+
R \frac{di(t)}{dt}
+
\frac{1}{C}i(t)
=
\frac{dV(t)}{dt}
$$

Por lo tanto:

$$
\boxed{
L \frac{d^2i(t)}{dt^2}
+
R \frac{di(t)}{dt}
+
\frac{1}{C}i(t)
=
\frac{dV(t)}{dt}
}
$$

---

## 5. Condiciones Iniciales

Las condiciones iniciales son:

$$
q(0) = q_0
$$

$$
i(0) = i_0
$$

El voltaje inicial del capacitor está relacionado con la carga mediante:

$$
q_0 = C V_C(0)
$$

Por lo tanto:

$$
q(0) = C V_C(0)
$$

---

## 6. Transformada de Laplace

Partimos de:

$$
Lq''(t) + Rq'(t) + \frac{1}{C}q(t) = V(t)
$$

Las transformadas necesarias son:

$$
\mathcal{L}\{q''(t)\}
=
s^2Q(s) - sq(0) - q'(0)
$$

$$
\mathcal{L}\{q'(t)\}
=
sQ(s) - q(0)
$$

Aplicando la transformada de Laplace:

$$
L
\left[
s^2Q(s)-sq(0)-q'(0)
\right]
+
R
\left[
sQ(s)-q(0)
\right]
+
\frac{1}{C}Q(s)
=
V(s)
$$

Agrupando:

$$
Q(s)
\left(
Ls^2+Rs+\frac{1}{C}
\right)
=
V(s)
+
Lsq(0)
+
Lq'(0)
+
Rq(0)
$$

Por lo tanto:

$$
\boxed{
Q(s)
=
\frac{
V(s)
+
Lsq(0)
+
Lq'(0)
+
Rq(0)
}{
Ls^2+Rs+\frac{1}{C}
}
}
$$

---

## 7. Condiciones Iniciales Cero

Si:

$$
q(0)=0
$$

y:

$$
i(0)=q'(0)=0
$$

entonces:

$$
\boxed{
Q(s)
=
\frac{V(s)}
{Ls^2+Rs+\frac{1}{C}}
}
$$

Como:

$$
I(s)=sQ(s)
$$

se obtiene:

$$
\boxed{
I(s)
=
\frac{sV(s)}
{Ls^2+Rs+\frac{1}{C}}
}
$$

Por lo tanto, la función de transferencia es:

$$
\boxed{
\frac{I(s)}{V(s)}
=
\frac{s}
{Ls^2+Rs+\frac{1}{C}}
}
$$

---

## 8. Entrada Escalón

Para una entrada escalón:

$$
V(t)=V_0u(t)
$$

su transformada de Laplace es:

$$
V(s)=\frac{V_0}{s}
$$

Entonces:

$$
\boxed{
Q(s)
=
\frac{V_0}
{
s
\left(
Ls^2+Rs+\frac{1}{C}
\right)
}
}
$$

Para la corriente:

$$
I(s)=sQ(s)
$$

por lo tanto:

$$
\boxed{
I(s)
=
\frac{V_0}
{Ls^2+Rs+\frac{1}{C}}
}
$$

---

## 9. Ecuación Característica

La ecuación característica es:

$$
Ls^2+Rs+\frac{1}{C}=0
$$

Dividiendo entre $L$:

$$
\boxed{
s^2+\frac{R}{L}s+\frac{1}{LC}=0
}
$$

---

## 10. Parámetros del Sistema

La frecuencia natural no amortiguada es:

$$
\boxed{
\omega_n=\frac{1}{\sqrt{LC}}
}
$$

El factor de amortiguamiento es:

$$
\boxed{
\alpha=\frac{R}{2L}
}
$$

El factor de amortiguamiento relativo es:

$$
\boxed{
\zeta=\frac{\alpha}{\omega_n}
}
$$

Para un sistema subamortiguado:

$$
\boxed{
\omega_d=\sqrt{\omega_n^2-\alpha^2}
}
$$

---

## 11. Tipos de Respuesta

### Sistema Subamortiguado

Se presenta cuando:

$$
\alpha < \omega_n
$$

Equivalentemente:

$$
R < 2\sqrt{\frac{L}{C}}
$$

La respuesta natural tiene la forma:

$$
q_n(t)
=
e^{-\alpha t}
\left[
A\cos(\omega_dt)
+
B\sin(\omega_dt)
\right]
$$

---

### Sistema Críticamente Amortiguado

Se presenta cuando:

$$
\alpha = \omega_n
$$

Equivalentemente:

$$
R = 2\sqrt{\frac{L}{C}}
$$

La respuesta natural tiene la forma:

$$
q_n(t)
=
(A+Bt)e^{-\alpha t}
$$

---

### Sistema Sobreamortiguado

Se presenta cuando:

$$
\alpha > \omega_n
$$

Equivalentemente:

$$
R > 2\sqrt{\frac{L}{C}}
$$

Los polos son:

$$
\boxed{
s_{1,2}
=
-\alpha
\pm
\sqrt{\alpha^2-\omega_n^2}
}
$$

---

# 12. Ejemplo Numérico

Consideremos:

$$
R=10\ \Omega
$$

$$
L=0.5\ H
$$

$$
C=0.01\ F
$$

y una fuente:

$$
V(t)=12u(t)
$$

La ecuación diferencial es:

$$
0.5q''(t)
+
10q'(t)
+
100q(t)
=
12
$$

Dividiendo entre $0.5$:

$$
\boxed{
q''(t)+20q'(t)+200q(t)=24
}
$$

---

## 13. Parámetros del Ejemplo

Factor de amortiguamiento:

$$
\alpha
=
\frac{10}{2(0.5)}
=
10\ \text{s}^{-1}
$$

Frecuencia natural:

$$
\omega_n
=
\frac{1}{\sqrt{(0.5)(0.01)}}
\approx
14.142\ \text{rad/s}
$$

Como:

$$
\alpha < \omega_n
$$

el sistema es:

$$
\boxed{
\text{SUBAMORTIGUADO}
}
$$

La frecuencia amortiguada es:

$$
\omega_d
=
\sqrt{14.142^2-10^2}
=
10\ \text{rad/s}
$$

El factor de amortiguamiento relativo es:

$$
\zeta
=
\frac{10}{14.142}
\approx
0.707
$$

---

## 14. Transformada de Laplace del Ejemplo

Para condiciones iniciales cero:

$$
Q(s)
=
\frac{12/s}
{0.5s^2+10s+100}
$$

Simplificando:

$$
\boxed{
Q(s)
=
\frac{24}
{s(s^2+20s+200)}
}
$$

Para la corriente:

$$
I(s)=sQ(s)
$$

por lo tanto:

$$
\boxed{
I(s)
=
\frac{24}
{s^2+20s+200}
}
$$

Completando el cuadrado:

$$
s^2+20s+200
=
(s+10)^2+100
$$

Por lo tanto:

$$
\boxed{
I(s)
=
\frac{24}
{(s+10)^2+10^2}
}
$$

---

## 15. Solución Temporal

La ecuación característica es:

$$
s^2+20s+200=0
$$

Las raíces son:

$$
\boxed{
s_1=-10+10j
}
$$

$$
\boxed{
s_2=-10-10j
}
$$

Los polos son complejos conjugados, confirmando que el sistema es subamortiguado.

### Carga del capacitor

La carga final es:

$$
q(\infty)=CV_0
$$

Entonces:

$$
q(\infty)
=
(0.01)(12)
=
0.12\ C
$$

La solución temporal de la carga es:

$$
\boxed{
q(t)
=
0.12
-
0.12e^{-10t}\cos(10t)
-
0.12e^{-10t}\sin(10t)
}
$$

También puede escribirse como:

$$
\boxed{
q(t)
=
0.12
\left[
1
-
e^{-10t}\cos(10t)
-
e^{-10t}\sin(10t)
\right]
}
$$

### Corriente

La corriente se obtiene mediante:

$$
i(t)=\frac{dq(t)}{dt}
$$

Por lo tanto:

$$
\boxed{
i(t)
=
2.4e^{-10t}\sin(10t)\ A
}
$$

La corriente presenta una respuesta oscilatoria amortiguada y tiende a cero cuando:

$$
t\rightarrow\infty
$$

---

## 16. Interpretación Física

Para una entrada escalón de $12\ V$, el capacitor termina almacenando:

$$
q(\infty)=0.12\ C
$$

El voltaje final del capacitor es:

$$
V_C(\infty)
=
\frac{q(\infty)}{C}
$$

Por lo tanto:

$$
V_C(\infty)
=
\frac{0.12}{0.01}
=
12\ V
$$

La corriente tiende a cero debido a que, en estado estacionario de corriente continua, el capacitor se comporta como un circuito abierto.

El sistema es subamortiguado porque la energía almacenada en el inductor y el capacitor produce oscilaciones que son disipadas progresivamente por la resistencia.

---

# 17. Programa en Python

El repositorio contiene un programa desarrollado en Python que permite realizar automáticamente el análisis del circuito RLC.

El programa permite introducir:

- Resistencia $R$.
- Inductancia $L$.
- Capacitancia $C$.
- Voltaje de la fuente $V_0$.
- Voltaje inicial del capacitor.
- Corriente inicial.
- Tiempo de simulación.

El programa calcula:

1. La ecuación diferencial.
2. La ecuación característica.
3. El factor de amortiguamiento.
4. La frecuencia natural.
5. La frecuencia amortiguada.
6. El factor de amortiguamiento relativo.
7. El tipo de respuesta.
8. La transformada de Laplace.
9. $Q(s)$.
10. $I(s)$.
11. La solución temporal $q(t)$.
12. La corriente $i(t)$.
13. Las gráficas del sistema.

---

# 18. Ejecución

Primero instalar las dependencias:

```bash
pip install -r requirements.txt
