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

Su voltaje está dado por:

$$
V_L(t) = L \frac{di(t)}{dt}
$$

### Capacitor

El capacitor almacena energía en forma de campo eléctrico.

Su voltaje está dado por:

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

$$
V(t) = V_R(t) + V_L(t) + V_C(t)
$$

Sustituyendo las expresiones de cada elemento:

$$
V(t) =
R i(t)
+
L \frac{di(t)}{dt}
+
\frac{q(t)}{C}
$$

Como:

$$
i(t) = \frac{dq(t)}{dt}
$$

entonces:

$$
\frac{di(t)}{dt}
=
\frac{d^2q(t)}{dt^2}
$$

Por lo tanto:

$$
V(t) =
R \frac{dq(t)}{dt}
+
L \frac{d^2q(t)}{dt^2}
+
\frac{q(t)}{C}
$$

Reordenando:

$$
L \frac{d^2q(t)}{dt^2}
+
R \frac{dq(t)}{dt}
+
\frac{1}{C}q(t)
=
V(t)
$$

Esta es la ecuación diferencial de segundo orden del circuito RLC utilizando la carga $q(t)$ como variable.

---

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

Utilizando:

$$
i(t) = \frac{dq(t)}{dt}
$$

y derivando ambos lados:

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
L \frac{d^2i(t)}{dt^2}
+
R \frac{di(t)}{dt}
+
\frac{1}{C}i(t)
=
\frac{dV(t)}{dt}
$$

Esta expresión representa el circuito utilizando la corriente $i(t)$ como variable de salida.

---

## 5. Condiciones Iniciales

Las condiciones iniciales del circuito pueden expresarse como:

$$
q(0) = q_0
$$

y:

$$
i(0) = i_0
$$

El voltaje inicial del capacitor está relacionado con la carga inicial mediante:

$$
q_0 = C V_C(0)
$$

Por lo tanto:

$$
q(0) = C V_C(0)
$$

Estas condiciones iniciales son necesarias para obtener la solución completa del circuito.

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

y:

$$
\mathcal{L}\{q'(t)\}
=
sQ(s) - q(0)
$$

Aplicando la transformada de Laplace:

$$
L
\left[
s^2Q(s) - sq(0) - q'(0)
\right]
+
R
\left[
sQ(s) - q(0)
\right]
+
\frac{1}{C}Q(s)
=
V(s)
$$

Agrupando los términos:

$$
Q(s)
\left(
Ls^2 + Rs + \frac{1}{C}
\right)
=
V(s)
+
Ls q(0)
+
Lq'(0)
+
Rq(0)
$$

Por lo tanto:

$$
Q(s)
=
\frac{
V(s)
+
Ls q(0)
+
Lq'(0)
+
Rq(0)
}{
Ls^2 + Rs + \frac{1}{C}
}
$$

---

## 7. Condiciones Iniciales Cero

Si:

$$
q(0) = 0
$$

y:

$$
i(0) = q'(0) = 0
$$

entonces:

$$
Q(s)
=
\frac{V(s)}
{Ls^2 + Rs + \frac{1}{C}}
$$

Como:

$$
I(s) = sQ(s)
$$

se obtiene:

$$
I(s)
=
\frac{sV(s)}
{Ls^2 + Rs + \frac{1}{C}}
$$

Por lo tanto, la función de transferencia entre el voltaje de entrada y la corriente es:

$$
\frac{I(s)}{V(s)}
=
\frac{s}
{Ls^2 + Rs + \frac{1}{C}}
$$

---

## 8. Entrada Escalón

Para una entrada escalón:

$$
V(t) = V_0u(t)
$$

su transformada de Laplace es:

$$
V(s) = \frac{V_0}{s}
$$

Sustituyendo:

$$
Q(s)
=
\frac{V_0}
{s
\left(
Ls^2 + Rs + \frac{1}{C}
\right)}
$$

Para la corriente:

$$
I(s) = sQ(s)
$$

por lo tanto:

$$
I(s)
=
\frac{V_0}
{Ls^2 + Rs + \frac{1}{C}}
$$

---

## 9. Ecuación Característica

La ecuación característica se obtiene a partir del denominador:

$$
Ls^2 + Rs + \frac{1}{C} = 0
$$

Dividiendo entre $L$:

$$
s^2 + \frac{R}{L}s + \frac{1}{LC} = 0
$$

Esta ecuación permite determinar los polos del sistema.

---

## 10. Parámetros del Sistema

La frecuencia natural no amortiguada es:

$$
\omega_n = \frac{1}{\sqrt{LC}}
$$

El factor de amortiguamiento es:

$$
\alpha = \frac{R}{2L}
$$

El factor de amortiguamiento relativo es:

$$
\zeta = \frac{\alpha}{\omega_n}
$$

Cuando el sistema es subamortiguado, la frecuencia amortiguada es:

$$
\omega_d =
\sqrt{\omega_n^2 - \alpha^2}
$$

---

## 11. Tipos de Respuesta

El comportamiento del circuito depende de los valores de $R$, $L$ y $C$.

### Sistema Subamortiguado

Se presenta cuando:

$$
\alpha < \omega_n
$$

Equivalentemente:

$$
R < 2\sqrt{\frac{L}{C}}
$$

El sistema presenta oscilaciones que disminuyen progresivamente con el tiempo.

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

### Sistema Críticamente Amortiguado

Se presenta cuando:

$$
\alpha = \omega_n
$$

Equivalentemente:

$$
R = 2\sqrt{\frac{L}{C}}
$$

El sistema regresa al equilibrio sin presentar oscilaciones.

La respuesta natural tiene la forma:

$$
q_n(t)
=
(A + Bt)e^{-\alpha t}
$$

### Sistema Sobreamortiguado

Se presenta cuando:

$$
\alpha > \omega_n
$$

Equivalentemente:

$$
R > 2\sqrt{\frac{L}{C}}
$$

El sistema no presenta oscilaciones y posee dos polos reales diferentes.

Los polos son:

$$
s_{1,2}
=
-\alpha
\pm
\sqrt{\alpha^2 - \omega_n^2}
$$

---

# 12. Ejemplo Numérico

Consideremos los siguientes valores:

$$
R = 10\ \Omega
$$

$$
L = 0.5\ H
$$

$$
C = 0.01\ F
$$

y una fuente escalón:

$$
V(t) = 12u(t)
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

Dividiendo toda la ecuación entre $0.5$:

$$
q''(t)
+
20q'(t)
+
200q(t)
=
24
$$

---

## 13. Parámetros del Ejemplo

El factor de amortiguamiento es:

$$
\alpha
=
\frac{R}{2L}
$$

Sustituyendo:

$$
\alpha
=
\frac{10}{2(0.5)}
=
10\ \text{s}^{-1}
$$

La frecuencia natural es:

$$
\omega_n
=
\frac{1}{\sqrt{LC}}
$$

Sustituyendo:

$$
\omega_n
=
\frac{1}{\sqrt{(0.5)(0.01)}}
\approx
14.142\ \text{rad/s}
$$

Como:

$$
10 < 14.142
$$

el sistema es subamortiguado.

La frecuencia amortiguada es:

$$
\omega_d
=
\sqrt{\omega_n^2 - \alpha^2}
$$

Entonces:

$$
\omega_d
=
\sqrt{14.142^2 - 10^2}
$$

Por lo tanto:

$$
\omega_d = 10\ \text{rad/s}
$$

El factor de amortiguamiento relativo es:

$$
\zeta
=
\frac{\alpha}{\omega_n}
$$

por lo tanto:

$$
\zeta
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
{0.5s^2 + 10s + 100}
$$

Multiplicando numerador y denominador por $2$:

$$
Q(s)
=
\frac{24}
{s(s^2 + 20s + 200)}
$$

Para la corriente:

$$
I(s) = sQ(s)
$$

por lo tanto:

$$
I(s)
=
\frac{24}
{s^2 + 20s + 200}
$$

Completando el cuadrado:

$$
s^2 + 20s + 200
=
(s + 10)^2 + 100
$$

Por lo tanto:

$$
I(s)
=
\frac{24}
{(s + 10)^2 + 10^2}
$$

---

## 15. Solución Temporal

La ecuación característica es:

$$
s^2 + 20s + 200 = 0
$$

Aplicando la fórmula cuadrática:

$$
s
=
\frac{-20 \pm \sqrt{20^2 - 4(200)}}{2}
$$

$$
s
=
\frac{-20 \pm \sqrt{-400}}{2}
$$

Por lo tanto:

$$
s_1 = -10 + 10j
$$

$$
s_2 = -10 - 10j
$$

Los polos son complejos conjugados, confirmando que el sistema es subamortiguado.

### Carga del capacitor

La carga final es:

$$
q(\infty) = CV_0
$$

Sustituyendo:

$$
q(\infty)
=
(0.01)(12)
=
0.12\ C
$$

La solución de la carga es:

$$
q(t)
=
0.12
-
0.12e^{-10t}\cos(10t)
-
0.12e^{-10t}\sin(10t)
$$

También puede escribirse como:

$$
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
$$

### Corriente

La corriente se obtiene mediante:

$$
i(t) = \frac{dq(t)}{dt}
$$

Derivando:

$$
i(t)
=
2.4e^{-10t}\sin(10t)
$$

Por lo tanto:

$$
i(t)
=
2.4e^{-10t}\sin(10t)\ A
$$

La corriente presenta una respuesta oscilatoria amortiguada y tiende a cero cuando:

$$
t \rightarrow \infty
$$

---

## 16. Interpretación Física

Para una entrada escalón de $12\ V$, el capacitor termina almacenando una carga de:

$$
q(\infty) = 0.12\ C
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

# 17. Programa

El repositorio contiene un programa desarrollado en Python que permite realizar automáticamente el análisis del circuito RLC.

El usuario puede introducir:

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
