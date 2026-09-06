# 2. Sistema de Dos Tanques

A continuación se muestra el sistema de dos tanques utilizado para realizar el análisis.

![Sistema de dos tanques](ejercicio-2.png)

**Figura 2.** Sistema de dos tanques en serie.

El sistema está compuesto por dos tanques conectados en serie. El primer tanque tiene un área transversal $A_1$ y una altura de líquido $h_1(t)$, mientras que el segundo tanque tiene un área transversal $A_2$ y una altura de líquido $h_2(t)$.

El flujo de entrada al primer tanque se representa mediante $q_i(t)$, el flujo que pasa del primer tanque al segundo mediante $q_m(t)$ y el flujo de salida del segundo tanque mediante $q_o(t)$.

Las válvulas de entrada y salida se representan mediante los coeficientes $a_1$ y $a_2$, respectivamente.

El objetivo es obtener las ecuaciones diferenciales que representan el comportamiento del sistema y posteriormente obtener su función de transferencia mediante la transformada de Laplace.

---

# 3. Ecuaciones de los Tanques

## 3.1 Primer Tanque

El volumen de líquido almacenado en el primer tanque está dado por:

$$V_1(t)=A_1h_1(t)$$

La variación del volumen respecto al tiempo es:

$$\frac{dV_1(t)}{dt}=A_1\frac{dh_1(t)}{dt}$$

Aplicando el principio de conservación de masa, el flujo que entra al primer tanque menos el flujo que sale es igual a la variación del volumen:

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

El flujo que pasa del primer tanque al segundo depende de la altura del líquido en el primer tanque. Se considera la siguiente relación:

$$q_m(t)=a_1\sqrt{h_1(t)}$$

El flujo de salida del segundo tanque depende de la altura del líquido en el segundo tanque:

$$q_o(t)=a_2\sqrt{h_2(t)}$$

donde $a_1$ y $a_2$ representan los coeficientes de las válvulas.

Por lo tanto, las ecuaciones del sistema son:

$$A_1\frac{dh_1(t)}{dt}=q_i(t)-a_1\sqrt{h_1(t)}$$

$$A_2\frac{dh_2(t)}{dt}=a_1\sqrt{h_1(t)}-a_2\sqrt{h_2(t)}$$

Estas ecuaciones representan el modelo no lineal del sistema de dos tanques.

---

# 5. Condiciones de Operación

Para obtener la función de transferencia es necesario considerar un punto de operación del sistema.

Los valores de equilibrio se representan mediante:

$$h_1(t)=h_{10}$$

$$h_2(t)=h_{20}$$

$$q_i(t)=q_{i0}$$

$$q_m(t)=q_{m0}$$

$$q_o(t)=q_{o0}$$

En estado estacionario, las alturas de los tanques permanecen constantes, por lo que:

$$\frac{dh_1(t)}{dt}=0$$

$$\frac{dh_2(t)}{dt}=0$$

Por lo tanto:

$$q_{i0}=q_{m0}=q_{o0}$$

Además:

$$q_{m0}=a_1\sqrt{h_{10}}$$

$$q_{o0}=a_2\sqrt{h_{20}}$$

---

# 6. Linealización del Sistema

Debido a que las ecuaciones contienen las funciones $\sqrt{h_1(t)}$ y $\sqrt{h_2(t)}$, el sistema es no lineal.

Para obtener una función de transferencia se realiza una linealización alrededor del punto de operación.

Se definen las variables de perturbación:

$$h_1(t)=h_{10}+\Delta h_1(t)$$

$$h_2(t)=h_{20}+\Delta h_2(t)$$

$$q_i(t)=q_{i0}+\Delta q_i(t)$$

$$q_m(t)=q_{m0}+\Delta q_m(t)$$

$$q_o(t)=q_{o0}+\Delta q_o(t)$$

Para el flujo entre los tanques:

$$q_m(t)=a_1\sqrt{h_1(t)}$$

Linealizando alrededor del punto de operación $h_{10}$:

$$\Delta q_m(t)=\frac{a_1}{2\sqrt{h_{10}}}\Delta h_1(t)$$

Se define:

$$k_1=\frac{a_1}{2\sqrt{h_{10}}}$$

Por lo tanto:

$$\Delta q_m(t)=k_1\Delta h_1(t)$$

Para el flujo de salida:

$$q_o(t)=a_2\sqrt{h_2(t)}$$

Linealizando alrededor del punto de operación $h_{20}$:

$$\Delta q_o(t)=\frac{a_2}{2\sqrt{h_{20}}}\Delta h_2(t)$$

Se define:

$$k_2=\frac{a_2}{2\sqrt{h_{20}}}$$

Por lo tanto:

$$\Delta q_o(t)=k_2\Delta h_2(t)$$

---

# 7. Obtención de las Ecuaciones Diferenciales

Partimos de las ecuaciones de conservación de masa:

$$A_1\frac{dh_1(t)}{dt}=q_i(t)-q_m(t)$$

$$A_2\frac{dh_2(t)}{dt}=q_m(t)-q_o(t)$$

Después de realizar la linealización se obtienen las siguientes ecuaciones:

$$A_1\frac{d\Delta h_1(t)}{dt}=\Delta q_i(t)-\Delta q_m(t)$$

$$A_2\frac{d\Delta h_2(t)}{dt}=\Delta q_m(t)-\Delta q_o(t)$$

Sustituyendo las relaciones linealizadas de los flujos:

$$A_1\frac{d\Delta h_1(t)}{dt}=\Delta q_i(t)-k_1\Delta h_1(t)$$

$$A_2\frac{d\Delta h_2(t)}{dt}=k_1\Delta h_1(t)-k_2\Delta h_2(t)$$

Ordenando los términos:

$$A_1\frac{d\Delta h_1(t)}{dt}+k_1\Delta h_1(t)=\Delta q_i(t)$$

$$A_2\frac{d\Delta h_2(t)}{dt}+k_2\Delta h_2(t)=k_1\Delta h_1(t)$$

Estas ecuaciones diferenciales describen el comportamiento dinámico del sistema de dos tanques.

---

# 8. Condiciones Iniciales

Para aplicar correctamente la transformada de Laplace se consideran las condiciones iniciales de las variaciones de altura.

Las condiciones iniciales son:

$$\Delta h_1(0)=0$$

$$\Delta h_2(0)=0$$

Estas condiciones permiten obtener la función de transferencia del sistema considerando condiciones iniciales cero.

---

# 9. Transformada de Laplace

Partimos de la primera ecuación diferencial:

$$A_1\frac{d\Delta h_1(t)}{dt}+k_1\Delta h_1(t)=\Delta q_i(t)$$

Aplicando la transformada de Laplace:

$$A_1s\Delta H_1(s)+k_1\Delta H_1(s)=\Delta Q_i(s)$$

Factorizando $\Delta H_1(s)$:

$$\Delta H_1(s)[A_1s+k_1]=\Delta Q_i(s)$$

Despejando:

$$\Delta H_1(s)=\frac{\Delta Q_i(s)}{A_1s+k_1}$$

Ahora se aplica la transformada de Laplace a la segunda ecuación diferencial:

$$A_2\frac{d\Delta h_2(t)}{dt}+k_2\Delta h_2(t)=k_1\Delta h_1(t)$$

Aplicando la transformada de Laplace:

$$A_2s\Delta H_2(s)+k_2\Delta H_2(s)=k_1\Delta H_1(s)$$

Factorizando $\Delta H_2(s)$:

$$\Delta H_2(s)[A_2s+k_2]=k_1\Delta H_1(s)$$

Despejando:

$$\Delta H_2(s)=\frac{k_1\Delta H_1(s)}{A_2s+k_2}$$

Sustituyendo la expresión de $\Delta H_1(s)$:

$$\Delta H_2(s)=\frac{k_1\Delta Q_i(s)}{(A_1s+k_1)(A_2s+k_2)}$$

---

# 10. Función de Transferencia

La salida del sistema corresponde al flujo de salida $\Delta q_o(t)$.

La relación entre el flujo de salida y la altura del segundo tanque es:

$$\Delta q_o(t)=k_2\Delta h_2(t)$$

Aplicando la transformada de Laplace:

$$\Delta Q_o(s)=k_2\Delta H_2(s)$$

Sustituyendo la expresión obtenida para $\Delta H_2(s)$:

$$\Delta Q_o(s)=\frac{k_1k_2\Delta Q_i(s)}{(A_1s+k_1)(A_2s+k_2)}$$

La función de transferencia se define como la relación entre la salida y la entrada:

$$G(s)=\frac{\Delta Q_o(s)}{\Delta Q_i(s)}$$

Por lo tanto, la función de transferencia del sistema de dos tanques es:

$$G(s)=\frac{k_1k_2}{(A_1s+k_1)(A_2s+k_2)}$$

Donde:

$$k_1=\frac{a_1}{2\sqrt{h_{10}}}$$

$$k_2=\frac{a_2}{2\sqrt{h_{20}}}$$

Sustituyendo estos valores:

$$G(s)=\frac{\frac{a_1}{2\sqrt{h_{10}}}\frac{a_2}{2\sqrt{h_{20}}}}{\left(A_1s+\frac{a_1}{2\sqrt{h_{10}}}\right)\left(A_2s+\frac{a_2}{2\sqrt{h_{20}}}\right)}$$

Esta expresión representa matemáticamente la relación entre la variación del flujo de entrada $\Delta Q_i(s)$ y la variación del flujo de salida $\Delta Q_o(s)$.

---

# 11. Conclusiones

El análisis del sistema de dos tanques permitió obtener un modelo matemático que representa el comportamiento dinámico del nivel de líquido en ambos tanques.

Mediante la Ley de Conservación de Masa se establecieron las ecuaciones correspondientes al primer y segundo tanque.

Para el primer tanque se obtuvo:

$$A_1\frac{dh_1(t)}{dt}=q_i(t)-q_m(t)$$

Para el segundo tanque se obtuvo:

$$A_2\frac{dh_2(t)}{dt}=q_m(t)-q_o(t)$$

Debido a que los flujos dependen de la raíz cuadrada de las alturas, el modelo inicial es no lineal. Por esta razón, se realizó una linealización alrededor de un punto de operación.

Posteriormente, se aplicó la transformada de Laplace considerando condiciones iniciales cero.

Finalmente, se obtuvo la función de transferencia:

$$G(s)=\frac{\Delta Q_o(s)}{\Delta Q_i(s)}=\frac{k_1k_2}{(A_1s+k_1)(A_2s+k_2)}$$

donde:

$$k_1=\frac{a_1}{2\sqrt{h_{10}}}$$

y:

$$k_2=\frac{a_2}{2\sqrt{h_{20}}}$$

Con esto se obtiene el modelo matemático y la función de transferencia del sistema de dos tanques conectados en serie.

