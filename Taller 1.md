# Sistemas de Control III - Circuito RLC

En este ejercicio se analiza un circuito eléctrico RLC conectado en serie con el objetivo de obtener la ecuación diferencial del sistema y posteriormente determinar su función de transferencia.

La entrada del sistema está representada por el voltaje \(e_i(t)\), mientras que la salida corresponde al voltaje \(e_o(t)\), medido en el capacitor.

---

## 1. Descripción del Circuito

El circuito está compuesto por tres elementos eléctricos:

- **\(R\):** Resistencia.
- **\(L\):** Inductancia.
- **\(C\):** Capacitancia.

Además, se tienen las siguientes variables:

- **\(e_i(t)\):** Voltaje de entrada.
- **\(e_o(t)\):** Voltaje de salida.
- **\(i(t)\):** Corriente que circula por el circuito.

Debido a que la resistencia, el inductor y el capacitor están conectados en serie, la corriente \(i(t)\) es la misma en los tres elementos.

La entrada del sistema es:

$$
e_i(t)
$$

La salida del sistema es:

$$
e_o(t)
$$

La salida \(e_o(t)\) corresponde al voltaje presente en el capacitor.

---

## 2. Ley de Voltajes de Kirchhoff

Para obtener la ecuación diferencial del sistema se utiliza la **Ley de Voltajes de Kirchhoff**.

Esta ley establece que la suma de las caídas de voltaje en una malla cerrada es igual al voltaje aplicado.

Por lo tanto:

$$
e_i(t)=e_R(t)+e_L(t)+e_C(t)
$$

Como el voltaje de salida se encuentra en el capacitor:

$$
e_C(t)=e_o(t)
$$

Entonces:

$$
e_i(t)=e_R(t)+e_L(t)+e_o(t)
$$

Esta expresión será utilizada para obtener la ecuación diferencial del circuito.

---

## 3. Ecuación de la Resistencia

Para la resistencia se utiliza la Ley de Ohm:

$$
e_R(t)=Ri(t)
$$

Donde:

- \(e_R(t)\) es el voltaje en la resistencia.
- \(R\) es el valor de la resistencia.
- \(i(t)\) es la corriente que circula por el circuito.

Por lo tanto:

$$
e_R(t)=Ri(t)
$$

---

## 4. Ecuación del Inductor

Para el inductor se utiliza la relación entre el voltaje y la corriente:

$$
e_L(t)=L\frac{di}{dt}
$$

Donde:

- \(e_L(t)\) es el voltaje en el inductor.
- \(L\) es la inductancia.
- \(i(t)\) es la corriente.
- \(di/dt\) representa la variación de la corriente con respecto al tiempo.

Por lo tanto:

$$
e_L(t)=L\frac{di}{dt}
$$

---

## 5. Ecuación del Capacitor

Para el capacitor se utiliza la relación:

$$
i(t)=C\frac{de_C}{dt}
$$

Como el voltaje del capacitor corresponde a la salida:

$$
e_C(t)=e_o(t)
$$

Entonces:

$$
i(t)=C\frac{de_o}{dt}
$$

Por lo tanto:

$$
i(t)=C\frac{de_o}{dt}
$$

Esta expresión permite representar la corriente del circuito en función del voltaje de salida.

---

## 6. Derivada de la Corriente

Para utilizar la ecuación del inductor necesitamos obtener la derivada de la corriente:

$$
\frac{di}{dt}
$$

Partimos de la ecuación obtenida para el capacitor:

$$
i(t)=C\frac{de_o}{dt}
$$

Derivando ambos lados con respecto al tiempo:

$$
\frac{di}{dt}
=
C\frac{d^2e_o}{dt^2}
$$

Por lo tanto:

$$
\frac{di}{dt}
=
C\frac{d^2e_o}{dt^2}
$$

---

## 7. Sustitución en la Ley de Kirchhoff

La ecuación de Kirchhoff obtenida anteriormente es:

$$
e_i(t)=e_R(t)+e_L(t)+e_o(t)
$$

Sustituyendo la ecuación de la resistencia:

$$
e_R(t)=Ri(t)
$$

y la ecuación del inductor:

$$
e_L(t)=L\frac{di}{dt}
$$

obtenemos:

$$
e_i(t)
=
Ri(t)
+
L\frac{di}{dt}
+
e_o(t)
$$

Ahora se sustituyen las expresiones obtenidas para el capacitor.

Sabemos que:

$$
i(t)=C\frac{de_o}{dt}
$$

y:

$$
\frac{di}{dt}
=
C\frac{d^2e_o}{dt^2}
$$

Sustituyendo:

$$
e_i(t)
=
R\left(C\frac{de_o}{dt}\right)
+
L\left(C\frac{d^2e_o}{dt^2}\right)
+
e_o(t)
$$

Realizando las multiplicaciones:

$$
e_i(t)
=
RC\frac{de_o}{dt}
+
LC\frac{d^2e_o}{dt^2}
+
e_o(t)
$$

---

## 8. Ecuación Diferencial

Ordenando los términos de acuerdo con el orden de las derivadas:

$$
LC\frac{d^2e_o}{dt^2}
+
RC\frac{de_o}{dt}
+
e_o(t)
=
e_i(t)
$$

Esta es la ecuación diferencial que describe el comportamiento dinámico del circuito RLC.

La ecuación es de segundo orden debido a la presencia del inductor y del capacitor.

---

## 9. Aplicación de la Transformada de Laplace

Para obtener la función de transferencia se aplica la Transformada de Laplace a la ecuación diferencial.

Partimos de:

$$
LC\frac{d^2e_o}{dt^2}
+
RC\frac{de_o}{dt}
+
e_o(t)
=
e_i(t)
$$

Para obtener la función de transferencia se consideran condiciones iniciales nulas:

$$
e_o(0)=0
$$

y:

$$
\frac{de_o}{dt}(0)=0
$$

Bajo estas condiciones:

$$
\mathcal{L}
\left\{
\frac{de_o}{dt}
\right\}
=
sE_o(s)
$$

Para la segunda derivada:

$$
\mathcal{L}
\left\{
\frac{d^2e_o}{dt^2}
\right\}
=
s^2E_o(s)
$$

Además:

$$
\mathcal{L}\{e_o(t)\}=E_o(s)
$$

y:

$$
\mathcal{L}\{e_i(t)\}=E_i(s)
$$

---

## 10. Ecuación en el Dominio de Laplace

Aplicando la Transformada de Laplace a la ecuación diferencial:

$$
LC\frac{d^2e_o}{dt^2}
+
RC\frac{de_o}{dt}
+
e_o(t)
=
e_i(t)
$$

se obtiene:

$$
LCs^2E_o(s)
+
RCsE_o(s)
+
E_o(s)
=
E_i(s)
$$

Esta es la representación algebraica del sistema en el dominio de Laplace.

---

## 11. Factorización de \(E_o(s)\)

Todos los términos del lado izquierdo contienen \(E_o(s)\).

Por lo tanto, se puede sacar como factor común:

$$
E_o(s)
\left(
LCs^2+RCs+1
\right)
=
E_i(s)
$$

Ahora se despeja \(E_o(s)\):

$$
E_o(s)
=
\frac{E_i(s)}
{LCs^2+RCs+1}
$$

---

## 12. Función de Transferencia

La función de transferencia se define como la relación entre la salida y la entrada en el dominio de Laplace, considerando condiciones iniciales nulas.

Por definición:

$$
G(s)=\frac{E_o(s)}{E_i(s)}
$$

A partir de la ecuación obtenida:

$$
E_o(s)
=
\frac{E_i(s)}
{LCs^2+RCs+1}
$$

se obtiene:

$$
G(s)
=
\frac{1}
{LCs^2+RCs+1}
$$

Por lo tanto, la función de transferencia del circuito es:

$$
\frac{E_o(s)}{E_i(s)}
=
\frac{1}
{LCs^2+RCs+1}
$$

---

## 13. Implementación en MATLAB

Para implementar el procedimiento en MATLAB se utilizan variables simbólicas.

Primero se definen las variables del circuito:

```matlab
clc;
clear;
close all;

syms R L C t s
syms ei(t) eo(t) i(t)
