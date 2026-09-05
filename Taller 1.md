# Sistemas de Control

# Circuito RLC en Serie

Este proyecto presenta el análisis matemático de un circuito RLC en serie
mediante ecuaciones diferenciales y la transformada de Laplace.

El objetivo es obtener el modelo matemático del sistema, analizar sus polos,
determinar el tipo de amortiguamiento y obtener la respuesta temporal de la
carga del capacitor y de la corriente.

---

## 1. Descripción del Sistema

Un circuito RLC en serie está compuesto por:

- Una resistencia $R$.
- Una inductancia $L$.
- Un capacitor de capacitancia $C$.
- Una fuente de voltaje $V(t)$.

Los tres elementos se encuentran conectados en serie, por lo que la misma
corriente $i(t)$ circula por todos los elementos.

El circuito RLC constituye un sistema dinámico de segundo orden y es utilizado
como modelo en el estudio de Sistemas de Control.

---

## 2. Ley de Kirchhoff

Aplicando la Ley de Kirchhoff de Voltajes:

$$
V(t)=V_R(t)+V_L(t)+V_C(t)
$$

Para cada elemento:

### Resistencia

$$
V_R(t)=Ri(t)
$$

### Inductor

$$
V_L(t)=L\frac{di(t)}{dt}
$$

### Capacitor

$$
V_C(t)=\frac{q(t)}{C}
$$

Además:

$$
i(t)=\frac{dq(t)}{dt}
$$

---

## 3. Ecuación Diferencial

Sustituyendo las expresiones anteriores:

$$
V(t)
=
R\frac{dq(t)}{dt}
+
L\frac{d^2q(t)}{dt^2}
+
\frac{q(t)}{C}
$$

Reordenando:

$$
\boxed{
L\frac{d^2q(t)}{dt^2}
+
R\frac{dq(t)}{dt}
+
\frac{1}{C}q(t)
=
V(t)
}
$$

Esta es la ecuación diferencial que describe el circuito RLC en términos de
la carga del capacitor.

---

## 4. Ecuación en función de la corriente

Como:

$$
i(t)=\frac{dq(t)}{dt}
$$

se puede derivar la ecuación anterior:

$$
\frac{dV(t)}{dt}
=
L\frac{d^2i(t)}{dt^2}
+
R\frac{di(t)}{dt}
+
\frac{1}{C}i(t)
$$

Por lo tanto:

$$
\boxed{
L\frac{d^2i(t)}{dt^2}
+
R\frac{di(t)}{dt}
+
\frac{1}{C}i(t)
=
\frac{dV(t)}{dt}
}
$$

Esta expresión es importante porque muestra que, cuando se utiliza la
corriente como variable, aparece la derivada de la fuente de voltaje.

---

## 5. Transformada de Laplace

Partimos de:

$$
Lq''(t)+Rq'(t)+\frac{1}{C}q(t)=V(t)
$$

Utilizando las propiedades de la transformada de Laplace:

$$
\mathcal{L}\{q'(t)\}
=
sQ(s)-q(0)
$$

y:

$$
\mathcal{L}\{q''(t)\}
=
s^2Q(s)-sq(0)-q'(0)
$$

Aplicando Laplace:

$$
L[s^2Q(s)-sq(0)-q'(0)]
+
R[sQ(s)-q(0)]
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
Q(s)=
\frac{
V(s)+Lsq(0)+Lq'(0)+Rq(0)
}{
Ls^2+Rs+\frac{1}{C}
}
}
$$

---

## 6. Condiciones Iniciales Cero

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
Q(s)=
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
I(s)=
\frac{sV(s)}
{Ls^2+Rs+\frac{1}{C}}
}
$$

Por lo tanto, la función de transferencia corriente/voltaje es:

$$
\boxed{
\frac{I(s)}{V(s)}
=
\frac{s}
{Ls^2+Rs+\frac{1}{C}}
}
$$

---

## 7. Entrada Escalón

Para una fuente de voltaje escalón:

$$
V(t)=V_0u(t)
$$

su transformada de Laplace es:

$$
V(s)=\frac{V_0}{s}
$$

Entonces:

$$
Q(s)
=
\frac{V_0}
{
s
\left(
Ls^2+Rs+\frac{1}{C}
\right)
}
$$

y:

$$
I(s)=sQ(s)
$$

por lo tanto:

$$
\boxed{
I(s)=
\frac{V_0}
{Ls^2+Rs+\frac{1}{C}}
}
$$

---

## 8. Parámetros del Sistema

Dividiendo la ecuación diferencial entre $L$:

$$
q''(t)
+
\frac{R}{L}q'(t)
+
\frac{1}{LC}q(t)
=
\frac{V(t)}{L}
$$

La frecuencia natural es:

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

La ecuación característica es:

$$
Ls^2+Rs+\frac{1}{C}=0
$$

o:

$$
s^2+\frac{R}{L}s+\frac{1}{LC}=0
$$

---

## 9. Tipos de Respuesta

El tipo de respuesta depende de la relación entre $\alpha$ y $\omega_n$.

### Sistema Subamortiguado

Si:

$$
\alpha<\omega_n
$$

el sistema presenta oscilaciones amortiguadas.

La frecuencia amortiguada es:

$$
\boxed{
\omega_d=
\sqrt{\omega_n^2-\alpha^2}
}
$$

La respuesta tiene la forma:

$$
q(t)
=
q_f+
e^{-\alpha t}
[
A\cos(\omega_dt)
+
B\sin(\omega_dt)
]
$$

---

### Sistema Críticamente Amortiguado

Si:

$$
\alpha=\omega_n
$$

el sistema alcanza el equilibrio sin oscilaciones.

La respuesta tiene la forma:

$$
q(t)
=
q_f+
(A+Bt)e^{-\alpha t}
$$

---

### Sistema Sobreamortiguado

Si:

$$
\alpha>\omega_n
$$

el sistema presenta dos polos reales diferentes:

$$
s_{1,2}
=
-\alpha
\pm
\sqrt{\alpha^2-\omega_n^2}
$$

La respuesta tiene la forma:

$$
q(t)
=
q_f+
Ae^{s_1t}
+
Be^{s_2t}
$$

---

## 10. Ejemplo Numérico

Se consideran los siguientes valores:

$$
R=10\ \Omega
$$

$$
L=0.5\ H
$$

$$
C=0.01\ F
$$

$$
V_0=12\ V
$$

con condiciones iniciales:

$$
q(0)=0
$$

$$
i(0)=0
$$

---

## 11. Ecuación Diferencial del Ejemplo

Sustituyendo los valores:

$$
0.5q''(t)+10q'(t)+100q(t)=12
$$

Dividiendo entre $0.5$:

$$
\boxed{
q''(t)+20q'(t)+200q(t)=24
}
$$

---

## 12. Análisis del Sistema

El factor de amortiguamiento es:

$$
\alpha
=
\frac{10}{2(0.5)}
=
10
$$

La frecuencia natural es:

$$
\omega_n
=
\frac{1}{\sqrt{(0.5)(0.01)}}
=
14.142
$$

Como:

$$
10<14.142
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
$$

por lo tanto:

$$
\boxed{
\omega_d=10\ rad/s
}
$$

---

## 13. Transformada de Laplace del Ejemplo

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

---

## 14. Polos del Sistema

La ecuación característica es:

$$
s^2+20s+200=0
$$

Las raíces son:

$$
s_1=-10+10j
$$

$$
s_2=-10-10j
$$

Los polos tienen parte real negativa, por lo que el sistema es estable.

---

## 15. Solución Temporal

La carga final del capacitor es:

$$
q_f=CV_0
$$

Por lo tanto:

$$
q_f=(0.01)(12)
$$

$$
q_f=0.12\ C
$$

La solución es:

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

La corriente se obtiene mediante:

$$
i(t)=\frac{dq(t)}{dt}
$$

por lo tanto:

$$
\boxed{
i(t)=
2.4e^{-10t}\sin(10t)
}
$$

---

## 16. Programa

El archivo `rlc.py` automatiza el procedimiento matemático.

El usuario puede introducir:

- Resistencia $R$.
- Inductancia $L$.
- Capacitancia $C$.
- Voltaje de la fuente.
- Voltaje inicial del capacitor.
- Corriente inicial.
- Tiempo de simulación.

El programa calcula:

1. La ecuación diferencial.
2. La ecuación normalizada.
3. La transformada de Laplace.
4. $Q(s)$.
5. $I(s)$.
6. $\alpha$.
7. $\omega_n$.
8. $\omega_d$, cuando corresponde.
9. Los polos del sistema.
10. El tipo de amortiguamiento.
11. La solución analítica.
12. La gráfica de $q(t)$.
13. La gráfica de $i(t)$.

---

## 17. Instalación

Se necesita Python 3.

Instalar las dependencias:

```bash
pip install -r requirements.txt
