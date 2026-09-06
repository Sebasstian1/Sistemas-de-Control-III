# 2. Sistema de Dos Tanques

A continuación se muestra el sistema de dos tanques utilizado para realizar el análisis.

![Sistema de dos tanques](ejercicio-2.png)

**Figura 2.** Sistema de dos tanques en serie.

El sistema está compuesto por dos tanques conectados en serie. El primer tanque tiene un área transversal $A_1$ y una altura de líquido $h_1(t)$, mientras que el segundo tanque tiene un área transversal $A_2$ y una altura de líquido $h_2(t)$.

El flujo de entrada al primer tanque se representa mediante $q_i(t)$, el flujo que pasa del primer tanque al segundo mediante $q_m(t)$ y el flujo de salida del segundo tanque mediante $q_o(t)$.

Las válvulas de los tanques se representan mediante los coeficientes $a_1$ y $a_2$.

El objetivo es obtener las ecuaciones diferenciales que representan el comportamiento del sistema y posteriormente obtener su función de transferencia mediante la transformada de Laplace.

---

# 3. Ecuaciones de los Tanques

## 3.1 Primer Tanque

El volumen de líquido almacenado en el primer tanque está dado por:

$$V_1(t)=A_1h_1(t)$$

La variación del volumen respecto al tiempo es:

$$\frac{dV_1(t)}{dt}=A_1\frac{dh_1(t)}{dt}$$

Aplicando la Ley de Conservación de Masa, el flujo que entra al primer tanque menos el flujo que sale es igual a la variación del volumen:

$$A_1\frac{dh_1(t)}{dt}=q_i(t)-q_m(t)$$

---

## 3.2 Segundo Tanque

El volumen de líquido almacenado en el segundo tanque está dado por:

$$V_2(t)=A_2h_2(t)$$

La variación del volumen respecto al tiempo es:

$$\frac{dV_2(t)}{dt}=A_2\frac{dh_2(t)}{dt}$$

En el segundo tanque entra el flujo $q_m(t)$ y sale el flujo $q_o(t)$.

Por lo tanto:

$$A_2\frac{dh_2(t)}{dt}=q_m(t)-q_o(t)$$

---

# 4. Ecuaciones de los Flujos

Para realizar el análisis del sistema se considera que el flujo que pasa del primer tanque al segundo es proporcional a la altura del primer tanque:

$$q_m(t)=a_1h_1(t)$$

De igual manera, el flujo de salida del segundo tanque es proporcional a la altura del segundo tanque:

$$q_o(t)=a_2h_2(t)$$

donde $a_1$ y $a_2$ representan los coeficientes de flujo de las válvulas.

Sustituyendo estas expresiones en las ecuaciones de los tanques:

$$A_1\frac{dh_1(t)}{dt}=q_i(t)-a_1h_1(t)$$

$$A_2\frac{dh_2(t)}{dt}=a_1h_1(t)-a_2h_2(t)$$

Estas ecuaciones representan el comportamiento dinámico del sistema de dos tanques.

---

# 5. Obtención de las Ecuaciones Diferenciales

Partimos de las ecuaciones obtenidas mediante la Ley de Conservación de Masa:

$$A_1\frac{dh_1(t)}{dt}=q_i(t)-a_1h_1(t)$$

$$A_2\frac{dh_2(t)}{dt}=a_1h_1(t)-a_2h_2(t)$$

Ordenando los términos:

$$A_1\frac{dh_1(t)}{dt}+a_1h_1(t)=q_i(t)$$

$$A_2\frac{dh_2(t)}{dt}+a_2h_2(t)=a_1h_1(t)$$

Estas ecuaciones diferenciales describen el comportamiento del sistema de dos tanques en serie.

---

# 6. Condiciones Iniciales

Para aplicar correctamente la transformada de Laplace se deben considerar las condiciones iniciales del sistema.

Las alturas iniciales de los tanques se representan mediante:

$$h_1(0)$$

$$h_2(0)$$

Para obtener la función de transferencia se consideran condiciones iniciales cero:

$$h_1(0)=0$$

$$h_2(0)=0$$

---

# 7. Transformada de Laplace

La transformada de Laplace permite transformar las ecuaciones diferenciales del dominio del tiempo al dominio de la variable $s$.

Partimos de la primera ecuación diferencial:

$$A_1\frac{dh_1(t)}{dt}+a_1h_1(t)=q_i(t)$$

Aplicando la transformada de Laplace:

$$A_1sH_1(s)+a_1H_1(s)=Q_i(s)$$

Factorizando $H_1(s)$:

$$H_1(s)[A_1s+a_1]=Q_i(s)$$

Despejando:

$$H_1(s)=\frac{Q_i(s)}{A_1s+a_1}$$

---

# 8. Transformada de Laplace del Segundo Tanque

Partimos de la segunda ecuación diferencial:

$$A_2\frac{dh_2(t)}{dt}+a_2h_2(t)=a_1h_1(t)$$

Aplicando la transformada de Laplace:

$$A_2sH_2(s)+a_2H_2(s)=a_1H_1(s)$$

Factorizando $H_2(s)$:

$$H_2(s)[A_2s+a_2]=a_1H_1(s)$$

Despejando:

$$H_2(s)=\frac{a_1H_1(s)}{A_2s+a_2}$$

Sustituyendo la expresión obtenida para $H_1(s)$:

$$H_2(s)=\frac{a_1Q_i(s)}{(A_1s+a_1)(A_2s+a_2)}$$

---

# 9. Función de Transferencia

La salida del sistema corresponde al flujo de salida $q_o(t)$.

De acuerdo con la relación establecida anteriormente:

$$q_o(t)=a_2h_2(t)$$

Aplicando la transformada de Laplace:

$$Q_o(s)=a_2H_2(s)$$

Sustituyendo la expresión obtenida para $H_2(s)$:

$$Q_o(s)=\frac{a_1a_2Q_i(s)}{(A_1s+a_1)(A_2s+a_2)}$$

La función de transferencia se define como la relación entre la salida y la entrada:

$$G(s)=\frac{Q_o(s)}{Q_i(s)}$$

Por lo tanto, la función de transferencia del sistema de dos tanques es:

$$G(s)=\frac{a_1a_2}{(A_1s+a_1)(A_2s+a_2)}$$

Esta expresión representa matemáticamente la relación entre el flujo de entrada $Q_i(s)$ y el flujo de salida $Q_o(s)$ del sistema.

---

# 10. Conclusiones

El análisis del sistema de dos tanques permitió obtener un modelo matemático que representa el comportamiento dinámico de los niveles de líquido.

Mediante la Ley de Conservación de Masa se obtuvieron las ecuaciones correspondientes a cada tanque.

Para el primer tanque se obtuvo:

$$A_1\frac{dh_1(t)}{dt}+a_1h_1(t)=q_i(t)$$

Para el segundo tanque se obtuvo:

$$A_2\frac{dh_2(t)}{dt}+a_2h_2(t)=a_1h_1(t)$$

Posteriormente, se aplicó la transformada de Laplace considerando condiciones iniciales cero, obteniendo las expresiones de los niveles de líquido en el dominio de $s$.

Finalmente, se obtuvo la función de transferencia:

$$G(s)=\frac{Q_o(s)}{Q_i(s)}=\frac{a_1a_2}{(A_1s+a_1)(A_2s+a_2)}$$

Con esto se obtiene el modelo matemático y la función de transferencia del sistema de dos tanques conectados en serie.
