# Sistemas de Control III - Circuito RLC

En este ejercicio se analiza un circuito eléctrico RLC conectado en serie con el objetivo de obtener la ecuación diferencial del sistema y posteriormente determinar su función de transferencia.

La entrada del sistema está representada por el voltaje \(e_i(t)\), mientras que la salida corresponde al voltaje \(e_o(t)\), medido en el capacitor.

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

La entrada y salida del sistema son:

$$
\boxed{\text{Entrada}=e_i(t)}
$$

$$
\boxed{\text{Salida}=e_o(t)}
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
\boxed{e_R(t)=Ri(t)}
$$

---

## 4. Ecuación del Inductor

Para el inductor se utiliza la relación entre el voltaje y la corriente:

$$
e_L(t)=L\frac{di(t)}{dt}
$$

Donde:

- \(e_L(t)\) es el voltaje en el inductor.
- \(L\) es la inductancia.
- \(i(t)\) es la corriente.
- \(\frac{di(t)}{dt}\) representa la variación de la corriente con respecto al tiempo.

Por lo tanto:

$$
\boxed{
e_L(t)=L\frac{di(t)}{dt}
}
$$

---

## 5. Ecuación del Capacitor

Para el capacitor se utiliza la relación:

$$
i(t)=C\frac{de_C(t)}{dt}
$$

Como el voltaje del capacitor corresponde a la salida:

$$
e_C(t)=e_o(t)
$$

Entonces:

$$
i(t)=C\frac{de_o(t)}{dt}
$$

Por lo tanto:

$$
\boxed{
i(t)=C\frac{de_o(t)}{dt}
}
$$

Esta expresión permite representar la corriente del circuito en función del voltaje de salida.

---

## 6. Derivada de la Corriente

Para utilizar la ecuación del inductor necesitamos obtener:

$$
\frac{di(t)}{dt}
$$

Partimos de la ecuación obtenida para el capacitor:

$$
i(t)=C\frac{de_o(t)}{dt}
$$

Derivando ambos lados con respecto al tiempo:

$$
\frac{di(t)}{dt}
=
C\frac{d^2e_o(t)}{dt^2}
$$

Por lo tanto:

$$
\boxed{
\frac{di(t)}{dt}
=
C\frac{d^2e_o(t)}{dt^2}
}
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
e_L(t)=L\frac{di(t)}{dt}
$$

obtenemos:

$$
e_i(t)
=
Ri(t)
+
L\frac{di(t)}{dt}
+
e_o(t)
$$

Ahora se sustituyen las expresiones obtenidas para el capacitor.

Sabemos que:

$$
i(t)=C\frac{de_o(t)}{dt}
$$

y:

$$
\frac{di(t)}{dt}
=
C\frac{d^2e_o(t)}{dt^2}
$$

Sustituyendo:

$$
e_i(t)
=
R\left(C\frac{de_o(t)}{dt}\right)
+
L\left(C\frac{d^2e_o(t)}{dt^2}\right)
+
e_o(t)
$$

Realizando las multiplicaciones:

$$
e_i(t)
=
RC\frac{de_o(t)}{dt}
+
LC\frac{d^2e_o(t)}{dt^2}
+
e_o(t)
$$

---

## 8. Ecuación Diferencial

Ordenando los términos de acuerdo con el orden de las derivadas:

$$
\boxed{
LC\frac{d^2e_o(t)}{dt^2}
+
RC\frac{de_o(t)}{dt}
+
e_o(t)
=
e_i(t)
}
$$

Esta es la ecuación diferencial que describe el comportamiento dinámico del circuito RLC.

La ecuación tiene segundo orden debido a la presencia del capacitor y del inductor.

---

## 9. Aplicación de la Transformada de Laplace

Para obtener la función de transferencia se aplica la Transformada de Laplace a la ecuación diferencial.

Partimos de:

$$
LC\frac{d^2e_o(t)}{dt^2}
+
RC\frac{de_o(t)}{dt}
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
\frac{de_o(0)}{dt}=0
$$

Bajo estas condiciones, las transformadas de las derivadas son:

$$
\mathcal{L}
\left\{
\frac{de_o(t)}{dt}
\right\}
=
sE_o(s)
$$

y:

$$
\mathcal{L}
\left\{
\frac{d^2e_o(t)}{dt^2}
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
LC\frac{d^2e_o(t)}{dt^2}
+
RC\frac{de_o(t)}{dt}
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
\boxed{
G(s)
=
\frac{1}
{LCs^2+RCs+1}
}
$$

Por lo tanto, la función de transferencia del circuito es:

$$
\boxed{
\frac{E_o(s)}{E_i(s)}
=
\frac{1}
{LCs^2+RCs+1}
}
$$

---

## 13. Implementación en MATLAB

Para implementar el procedimiento en MATLAB se utilizan variables simbólicas.

Primero se definen los parámetros del circuito:

```matlab
clc;
clear;
close all;

syms R L C t s
syms ei(t) eo(t) i(t)
```

Posteriormente se establecen las ecuaciones correspondientes a cada elemento.

### Resistencia

```matlab
eR = R*i(t);
```

Esta expresión representa:

$$
e_R(t)=Ri(t)
$$

### Inductor

```matlab
eL = L*diff(i(t),t);
```

Esta expresión representa:

$$
e_L(t)=L\frac{di(t)}{dt}
$$

### Capacitor

```matlab
iC = C*diff(eo(t),t);
```

Esta expresión representa:

$$
i(t)=C\frac{de_o(t)}{dt}
$$

### Derivada de la corriente

```matlab
di_dt = diff(iC,t);
```

Con esto MATLAB obtiene:

$$
\frac{di(t)}{dt}
=
C\frac{d^2e_o(t)}{dt^2}
$$

---

## 14. Obtención de la Ecuación Diferencial en MATLAB

La ecuación de Kirchhoff es:

$$
e_i(t)=e_R(t)+e_L(t)+e_o(t)
$$

Se sustituyen las expresiones obtenidas anteriormente:

```matlab
ecuacion_diferencial = ...
    ei(t) == R*iC + L*di_dt + eo(t);
```

MATLAB representa entonces la ecuación diferencial del sistema:

$$
\boxed{
LC\frac{d^2e_o(t)}{dt^2}
+
RC\frac{de_o(t)}{dt}
+
e_o(t)
=
e_i(t)
}
$$

---

## 15. Función de Transferencia en MATLAB

La función de transferencia obtenida matemáticamente es:

$$
G(s)
=
\frac{1}
{LCs^2+RCs+1}
$$

Esta expresión se puede representar simbólicamente en MATLAB mediante:

```matlab
G = 1/(L*C*s^2 + R*C*s + 1);
```

Finalmente, se muestra el resultado:

```matlab
disp('Funcion de transferencia:');
disp(G);
```

---

## 16. Programa Completo en MATLAB

El siguiente programa contiene todo el procedimiento desarrollado anteriormente:

```matlab
%% SISTEMAS DE CONTROL III
% Analisis de un circuito RLC serie
%
% Entrada: ei(t)
% Salida:  eo(t)

clc;
clear;
close all;

%% Definicion de variables

syms R L C t s
syms ei(t) eo(t) i(t)

%% Ley de Voltajes de Kirchhoff
%
% ei(t) = eR(t) + eL(t) + eo(t)

%% Ecuacion de la resistencia
%
% eR(t) = R*i(t)

eR = R*i(t);

%% Ecuacion del inductor
%
% eL(t) = L*di(t)/dt

eL = L*diff(i(t),t);

%% Ecuacion del capacitor
%
% i(t) = C*deo(t)/dt
%
% Como eo(t) es el voltaje del capacitor:

iC = C*diff(eo(t),t);

%% Derivada de la corriente
%
% di(t)/dt = C*d2eo(t)/dt2

di_dt = diff(iC,t);

%% Ecuacion diferencial
%
% ei(t) = R*i(t) + L*di(t)/dt + eo(t)

ecuacion_diferencial = ...
    ei(t) == R*iC + L*di_dt + eo(t);

%% Mostrar ecuacion diferencial

disp(' ');
disp('==============================================');
disp('ECUACION DIFERENCIAL');
disp('==============================================');
disp(' ');

disp(ecuacion_diferencial);

%% Funcion de transferencia
%
% G(s) = Eo(s)/Ei(s)

G = 1/(L*C*s^2 + R*C*s + 1);

%% Mostrar funcion de transferencia

disp(' ');
disp('==============================================');
disp('FUNCION DE TRANSFERENCIA');
disp('==============================================');
disp(' ');

disp('G(s) = Eo(s)/Ei(s)');
disp(G);

%% Resultado general

disp(' ');
disp('==============================================');
disp('RESULTADO FINAL');
disp('==============================================');
disp(' ');

disp('Ecuacion diferencial:');
disp('LC*d2eo(t)/dt2 + RC*deo(t)/dt + eo(t) = ei(t)');

disp(' ');

disp('Funcion de transferencia:');
disp('G(s) = Eo(s)/Ei(s)');

disp('G(s) = 1/(LC*s^2 + RC*s + 1)');
```

---

## 17. Resultado Final

Después de realizar todo el procedimiento se obtiene la ecuación diferencial:

$$
\boxed{
LC\frac{d^2e_o(t)}{dt^2}
+
RC\frac{de_o(t)}{dt}
+
e_o(t)
=
e_i(t)
}
$$

Y la función de transferencia:

$$
\boxed{
G(s)
=
\frac{E_o(s)}{E_i(s)}
=
\frac{1}
{LCs^2+RCs+1}
}
$$

Por lo tanto, la relación entre la entrada \(e_i(t)\) y la salida \(e_o(t)\) del circuito RLC queda completamente determinada por:

$$
\boxed{
\frac{E_o(s)}{E_i(s)}
=
\frac{1}
{LCs^2+RCs+1}
}
$$

---

## 18. Conclusiones

A partir del análisis del circuito RLC se aplicó la Ley de Voltajes de Kirchhoff y las ecuaciones características de la resistencia, el inductor y el capacitor.

La corriente del circuito se expresó en función del voltaje de salida \(e_o(t)\), permitiendo eliminar la variable \(i(t)\) y obtener una ecuación diferencial únicamente en términos de la entrada \(e_i(t)\) y la salida \(e_o(t)\).

La ecuación diferencial obtenida fue:

$$
LC\frac{d^2e_o(t)}{dt^2}
+
RC\frac{de_o(t)}{dt}
+
e_o(t)
=
e_i(t)
$$

Posteriormente, mediante la Transformada de Laplace y considerando condiciones iniciales nulas, se obtuvo la función de transferencia:

$$
G(s)
=
\frac{E_o(s)}{E_i(s)}
=
\frac{1}
{LCs^2+RCs+1}
$$

Esta función de transferencia permite representar matemáticamente el comportamiento dinámico del circuito y puede utilizarse posteriormente para analizar la respuesta y las características del sistema.

---

## 19. Referencias

- Ogata, K. (2010). *Ingeniería de Control Moderna*. Pearson.
- Dorf, R. C., & Bishop, R. H. (2017). *Sistemas de Control Moderno*. Prentice Hall.
