# Circuito RLC en Serie

Este documento presenta el análisis de un circuito RLC en serie mediante
ecuaciones diferenciales y la transformada de Laplace. Se incluye la
obtención del modelo matemático a partir de la Ley de Kirchhoff, el análisis
de las condiciones iniciales y la solución del sistema.

---

## 1. Descripción del Sistema

Un circuito RLC en serie está compuesto por:

- Una resistencia $R$.
- Una inductancia $L$.
- Un capacitor de capacitancia $C$.
- Una fuente de voltaje $V(t)$.

Los tres elementos se encuentran conectados en serie, por lo que la misma
corriente $i(t)$ circula por todos ellos.

El circuito puede utilizarse para estudiar sistemas eléctricos de segundo
orden y presenta un comportamiento análogo a otros sistemas físicos como
el sistema masa-resorte-amortiguador.

---

## 2. Ley de Kirchhoff

Aplicando la Ley de Kirchhoff de Voltajes al circuito:

$$
V(t) = V_R(t) + V_L(t) + V_C(t)
$$

Los voltajes de cada elemento son:

### Resistencia

$$
V_R(t) = R i(t)
$$

### Inductor

$$
V_L(t) = L\frac{di(t)}{dt}
$$

### Capacitor

Para el capacitor se cumple:

$$
V_C(t) = \frac{q(t)}{C}
$$

Como la corriente es la derivada de la carga:

$$
i(t) = \frac{dq(t)}{dt}
$$

---

## 3. Ecuación Diferencial en función de la carga

Sustituyendo las expresiones anteriores en la Ley de Kirchhoff:

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

Esta es la ecuación diferencial de segundo orden que describe el
comportamiento del circuito RLC en serie.

---

## 4. Ecuación Diferencial en función de la corriente

Como:

$$
i(t)=\frac{dq(t)}{dt}
$$

derivamos la ecuación anterior:

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

Esta es la ecuación diferencial cuando se utiliza la corriente $i(t)$ como
variable de salida.

---

## 5. Transformada de Laplace

Partimos de la ecuación en términos de la carga:

$$
Lq''(t)+Rq'(t)+\frac{1}{C}q(t)=V(t)
$$

Aplicando la transformada de Laplace:

$$
\mathcal{L}\{q''(t)\}
=
s^2Q(s)-sq(0)-q'(0)
$$

y:

$$
\mathcal{L}\{q'(t)\}
=
sQ(s)-q(0)
$$

Por lo tanto:

$$
L[s^2Q(s)-sq(0)-q'(0)]
+
R[sQ(s)-q(0)]
+
\frac{1}{C}Q(s)
=
V(s)
$$

Agrupando los términos que contienen $Q(s)$:

$$
Q(s)
\left(
Ls^2+Rs+\frac{1}{C}
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

Finalmente:

$$
\boxed{
Q(s)=
\frac{
V(s)+Ls q(0)+Lq'(0)+Rq(0)
}{
Ls^2+Rs+\frac{1}{C}
}
}
$$

---

## 6. Condiciones Iniciales Cero

Para condiciones iniciales:

$$
q(0)=0
$$

y:

$$
i(0)=q'(0)=0
$$

la expresión anterior se simplifica a:

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

También puede escribirse la función de transferencia corriente/voltaje como:

$$
\boxed{
\frac{I(s)}{V(s)}
=
\frac{1}
{Ls+R+\frac{1}{Cs}}
}
$$

o equivalentemente:

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

Si la fuente de voltaje es un escalón:

$$
V(t)=V_0u(t)
$$

su transformada de Laplace es:

$$
V(s)=\frac{V_0}{s}
$$

Por lo tanto:

$$
Q(s)=
\frac{V_0}
{s\left(Ls^2+Rs+\frac{1}{C}\right)}
$$

y para la corriente:

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

## 8. Forma Normalizada

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

La ecuación característica correspondiente al sistema homogéneo es:

$$
Ls^2+Rs+\frac{1}{C}=0
$$

o:

$$
s^2+
\frac{R}{L}s+
\frac{1}{LC}=0
$$

---

## 9. Parámetros del Sistema

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

La frecuencia amortiguada, cuando el sistema es subamortiguado, es:

$$
\boxed{
\omega_d=
\sqrt{\omega_n^2-\alpha^2}
}
$$

---

## 10. Tipos de Respuesta

El comportamiento del circuito depende de la relación entre $\alpha$ y
$\omega_n$.

### Sistema Subamortiguado

Si:

$$
\alpha<\omega_n
$$

entonces:

$$
R<2\sqrt{\frac{L}{C}}
$$

El circuito presenta oscilaciones amortiguadas.

La respuesta contiene términos de la forma:

$$
e^{-\alpha t}
\left[
A\cos(\omega_dt)+B\sin(\omega_dt)
\right]
$$

---

### Sistema Críticamente Amortiguado

Si:

$$
\alpha=\omega_n
$$

entonces:

$$
R=2\sqrt{\frac{L}{C}}
$$

El sistema retorna a su estado de equilibrio sin presentar oscilaciones.

La respuesta tiene la forma:

$$
(A+Bt)e^{-\alpha t}
$$

---

### Sistema Sobreamortiguado

Si:

$$
\alpha>\omega_n
$$

entonces:

$$
R>2\sqrt{\frac{L}{C}}
$$

El sistema no presenta oscilaciones y posee dos polos reales diferentes.

La respuesta tiene la forma:

$$
Ae^{s_1t}+Be^{s_2t}
$$

donde:

$$
s_{1,2}
=
-\alpha
\pm
\sqrt{\alpha^2-\omega_n^2}
$$

---

## 11. Solución para un Ejemplo

Consideremos los valores:

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
0.5q''(t)+10q'(t)+100q(t)=12
$$

Dividiendo entre $0.5$:

$$
\boxed{
q''(t)+20q'(t)+200q(t)=24
}
$$

Los parámetros son:

$$
\alpha=\frac{10}{2(0.5)}=10
$$

y:

$$
\omega_n=
\frac{1}{\sqrt{(0.5)(0.01)}}
=
14.142
$$

Como:

$$
\alpha<\omega_n
$$

el sistema es:

$$
\boxed{\text{SUBAMORTIGUADO}}
$$

La frecuencia amortiguada es:

$$
\omega_d=
\sqrt{14.142^2-10^2}
$$

por lo tanto:

$$
\omega_d\approx10
$$

---

## 12. Transformada de Laplace del Ejemplo

Con condiciones iniciales cero:

$$
Q(s)=
\frac{12/s}
{0.5s^2+10s+100}
$$

Multiplicando numerador y denominador:

$$
\boxed{
Q(s)=
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
I(s)=
\frac{24}
{s^2+20s+200}
}
$$

---

## 13. Solución Temporal del Ejemplo

La ecuación característica es:

$$
s^2+20s+200=0
$$

Sus raíces son:

$$
s_1=-10+10j
$$

$$
s_2=-10-10j
$$

Por lo tanto, la respuesta natural tiene la forma:

$$
q_n(t)
=
e^{-10t}
[
A\cos(10t)+B\sin(10t)
]
$$

La respuesta final del capacitor es:

$$
q(\infty)=CV_0
$$

por lo tanto:

$$
q(\infty)
=
(0.01)(12)
=
0.12\ C
$$

Con condiciones iniciales cero, la solución es:

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

La corriente es:

$$
i(t)=\frac{dq(t)}{dt}
$$

y resulta:

$$
\boxed{
i(t)=
0.24e^{-10t}\sin(10t)
}
$$

---

## 14. Programa

El repositorio contiene un programa en Python llamado `rlc.py`.

El programa permite introducir los valores:

- Resistencia $R$.
- Inductancia $L$.
- Capacitancia $C$.
- Voltaje $V_0$.
- Voltaje inicial del capacitor.
- Corriente inicial.
- Tiempo de simulación.

Además, calcula automáticamente:

1. La ecuación diferencial.
2. Los parámetros $\alpha$ y $\omega_n$.
3. El tipo de amortiguamiento.
4. La transformada de Laplace.
5. $Q(s)$.
6. $I(s)$.
7. La solución temporal.
8. La gráfica de carga y corriente.

---

## 15. Ejecución del Programa

Para instalar las librerías necesarias:

```bash
pip install -r requirements.txt
