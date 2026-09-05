# Sistemas de Control - Circuito RLC en Serie

Este proyecto presenta el análisis matemático de un circuito RLC en serie utilizando ecuaciones diferenciales y la transformada de Laplace.

El objetivo es obtener el modelo matemático del circuito a partir de la Ley de Kirchhoff, analizar sus condiciones iniciales, determinar el tipo de respuesta del sistema y obtener su solución temporal.

---

## 1. Descripción del Sistema

Un circuito RLC en serie está compuesto por:

- Una resistencia de valor R.
- Una inductancia de valor L.
- Un capacitor de capacitancia C.
- Una fuente de voltaje V(t).

Los tres elementos se encuentran conectados en serie, por lo que la misma corriente i(t) circula por la resistencia, el inductor y el capacitor.

El circuito RLC representa un sistema eléctrico de segundo orden y puede utilizarse como modelo para el estudio de sistemas dinámicos.

---

## 2. Elementos del Circuito

### Resistencia

La resistencia disipa energía en forma de calor.

Su voltaje está dado por:

V_R(t) = R · i(t)

### Inductor

El inductor almacena energía en forma de campo magnético.

Su voltaje está dado por:

V_L(t) = L · di(t)/dt

### Capacitor

El capacitor almacena energía en forma de campo eléctrico.

Su voltaje está dado por:

V_C(t) = q(t)/C

donde q(t) representa la carga eléctrica.

Además:

i(t) = dq(t)/dt

---

## 3. Ley de Kirchhoff

Aplicando la Ley de Kirchhoff de Voltajes:

V(t) = V_R(t) + V_L(t) + V_C(t)

Sustituyendo las expresiones de cada elemento:

V(t) = R · i(t) + L · di(t)/dt + q(t)/C

Como:

i(t) = dq(t)/dt

entonces:

di(t)/dt = d²q(t)/dt²

Por lo tanto:

V(t) = R · dq(t)/dt + L · d²q(t)/dt² + q(t)/C

Reordenando:

L · d²q(t)/dt² + R · dq(t)/dt + q(t)/C = V(t)

Esta es la ecuación diferencial de segundo orden del circuito RLC utilizando la carga q(t) como variable.

---

## 4. Ecuación Diferencial en Función de la Corriente

Partiendo de:

L · d²q(t)/dt² + R · dq(t)/dt + q(t)/C = V(t)

y utilizando:

i(t) = dq(t)/dt

se deriva toda la ecuación:

L · d²i(t)/dt² + R · di(t)/dt + i(t)/C = dV(t)/dt

Por lo tanto:

L · d²i(t)/dt² + R · di(t)/dt + i(t)/C = dV(t)/dt

Esta expresión representa el circuito utilizando la corriente i(t) como variable de salida.

---

## 5. Condiciones Iniciales

Las condiciones iniciales del circuito pueden expresarse como:

q(0) = q₀

i(0) = i₀

El voltaje inicial del capacitor está relacionado con la carga inicial mediante:

q₀ = C · V_C(0)

Por lo tanto:

q(0) = C · V_C(0)

Estas condiciones iniciales son necesarias para obtener la solución completa del circuito.

---

## 6. Transformada de Laplace

Partimos de:

L · q''(t) + R · q'(t) + q(t)/C = V(t)

Las transformadas necesarias son:

ℒ{q''(t)} = s²Q(s) - s·q(0) - q'(0)

ℒ{q'(t)} = sQ(s) - q(0)

Aplicando la transformada de Laplace:

L · [s²Q(s) - s·q(0) - q'(0)]
+ R · [sQ(s) - q(0)]
+ Q(s)/C
= V(s)

Agrupando los términos que contienen Q(s):

Q(s) · [L·s² + R·s + 1/C]

= V(s) + L·s·q(0) + L·q'(0) + R·q(0)

Por lo tanto:

Q(s) =
[V(s) + L·s·q(0) + L·q'(0) + R·q(0)]
/
[L·s² + R·s + 1/C]

---

## 7. Condiciones Iniciales Cero

Si:

q(0) = 0

y:

i(0) = q'(0) = 0

entonces:

Q(s) = V(s) / [L·s² + R·s + 1/C]

Como:

I(s) = s·Q(s)

se obtiene:

I(s) = s·V(s) / [L·s² + R·s + 1/C]

Por lo tanto, la función de transferencia entre el voltaje de entrada y la corriente es:

I(s)/V(s) = s / [L·s² + R·s + 1/C]

---

## 8. Entrada Escalón

Para una entrada escalón:

V(t) = V₀·u(t)

su transformada de Laplace es:

V(s) = V₀/s

Sustituyendo:

Q(s) =
V₀ /
{s · [L·s² + R·s + 1/C]}

Para la corriente:

I(s) = s·Q(s)

por lo tanto:

I(s) = V₀ / [L·s² + R·s + 1/C]

---

## 9. Ecuación Característica

La ecuación característica se obtiene a partir del denominador:

L·s² + R·s + 1/C = 0

Dividiendo entre L:

s² + (R/L)·s + 1/(L·C) = 0

Esta ecuación permite determinar los polos del sistema.

---

## 10. Parámetros del Sistema

La frecuencia natural no amortiguada es:

ωₙ = 1 / √(L·C)

El factor de amortiguamiento es:

α = R / (2·L)

El factor de amortiguamiento relativo es:

ζ = α / ωₙ

Cuando el sistema es subamortiguado, la frecuencia amortiguada es:

ω_d = √(ωₙ² - α²)

---

## 11. Tipos de Respuesta

El comportamiento del circuito depende de los valores de R, L y C.

### Sistema Subamortiguado

Se presenta cuando:

α < ωₙ

Equivalentemente:

R < 2·√(L/C)

El sistema presenta oscilaciones que disminuyen progresivamente con el tiempo.

La respuesta natural tiene la forma:

qₙ(t) = e^(-αt) · [A·cos(ω_d·t) + B·sin(ω_d·t)]

---

### Sistema Críticamente Amortiguado

Se presenta cuando:

α = ωₙ

Equivalentemente:

R = 2·√(L/C)

El sistema regresa al equilibrio sin presentar oscilaciones.

La respuesta natural tiene la forma:

qₙ(t) = (A + B·t)·e^(-αt)

---

### Sistema Sobreamortiguado

Se presenta cuando:

α > ωₙ

Equivalentemente:

R > 2·√(L/C)

El sistema no presenta oscilaciones y posee dos polos reales diferentes.

Los polos son:

s₁,₂ = -α ± √(α² - ωₙ²)

---

# 12. Ejemplo Numérico

Consideremos los siguientes valores:

R = 10 Ω

L = 0.5 H

C = 0.01 F

y una fuente escalón:

V(t) = 12·u(t)

La ecuación diferencial es:

0.5·q''(t) + 10·q'(t) + 100·q(t) = 12

Dividiendo toda la ecuación entre 0.5:

q''(t) + 20·q'(t) + 200·q(t) = 24

---

## 13. Parámetros del Ejemplo

El factor de amortiguamiento es:

α = R / (2·L)

α = 10 / [2·(0.5)]

α = 10 s⁻¹

La frecuencia natural es:

ωₙ = 1 / √(L·C)

ωₙ = 1 / √[(0.5)(0.01)]

ωₙ ≈ 14.142 rad/s

Como:

10 < 14.142

el sistema es:

SUBAMORTIGUADO

La frecuencia amortiguada es:

ω_d = √(ωₙ² - α²)

ω_d = √(14.142² - 10²)

ω_d = 10 rad/s

El factor de amortiguamiento relativo es:

ζ = α / ωₙ

ζ = 10 / 14.142

ζ ≈ 0.707

---

## 14. Transformada de Laplace del Ejemplo

Para condiciones iniciales cero:

Q(s) =
(12/s) /
(0.5·s² + 10·s + 100)

Simplificando:

Q(s) = 24 / [s·(s² + 20·s + 200)]

Para la corriente:

I(s) = s·Q(s)

por lo tanto:

I(s) = 24 / (s² + 20·s + 200)

Completando el cuadrado:

s² + 20·s + 200 = (s + 10)² + 100

Por lo tanto:

I(s) = 24 / [(s + 10)² + 10²]

---

## 15. Solución Temporal

La ecuación característica es:

s² + 20·s + 200 = 0

Aplicando la fórmula cuadrática:

s = [-20 ± √(20² - 4·200)] / 2

s = [-20 ± √(-400)] / 2

Por lo tanto:

s₁ = -10 + 10j

s₂ = -10 - 10j

Los polos son complejos conjugados, confirmando que el sistema es subamortiguado.

### Carga del capacitor

La carga final es:

q(∞) = C·V₀

q(∞) = (0.01)(12)

q(∞) = 0.12 C

La solución de la carga es:

q(t) =
0.12
- 0.12·e^(-10t)·cos(10t)
- 0.12·e^(-10t)·sin(10t)

También puede escribirse como:

q(t) =
0.12·[1 - e^(-10t)·cos(10t) - e^(-10t)·sin(10t)]

### Corriente

La corriente se obtiene mediante:

i(t) = dq(t)/dt

Derivando:

i(t) = 2.4·e^(-10t)·sin(10t)

Por lo tanto:

i(t) = 2.4·e^(-10t)·sin(10t) A

La corriente presenta una respuesta oscilatoria amortiguada y tiende a cero cuando:

t → ∞

---

## 16. Interpretación Física

Para una entrada escalón de 12 V, el capacitor termina almacenando una carga de:

q(∞) = 0.12 C

El voltaje final del capacitor es:

V_C(∞) = q(∞) / C

V_C(∞) = 0.12 / 0.01

V_C(∞) = 12 V

La corriente tiende a cero debido a que, en estado estacionario de corriente continua, el capacitor se comporta como un circuito abierto.

El sistema es subamortiguado porque la energía almacenada en el inductor y el capacitor produce oscilaciones que son disipadas progresivamente por la resistencia.

---

# 17. Programa

El repositorio contiene un programa desarrollado en Python que permite realizar automáticamente el análisis del circuito RLC.

El usuario puede introducir:

- Resistencia R.
- Inductancia L.
- Capacitancia C.
- Voltaje de la fuente V₀.
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
9. Q(s).
10. I(s).
11. La solución temporal q(t).
12. La corriente i(t).
13. Las gráficas del sistema.

---

# 18. Ejecución

Primero instalar las dependencias:

```bash
pip install -r requirements.txt
