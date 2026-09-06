# Análisis de un Circuito RLC en Serie


# 1. Circuito RLC en Serie

A continuación se muestra el circuito RLC en serie utilizado para realizar el análisis.

![Circuito RLC en serie](circuito-rlc.png)

**Figura 1.** Circuito RLC en serie.

Un circuito RLC en serie está compuesto por una resistencia $R$, una inductancia $L$ y un capacitor $C$ conectados en serie.

El voltaje de entrada del sistema se representa mediante $e_i(t)$ y el voltaje de salida $e_o(t)$ corresponde al voltaje medido en el capacitor.

Para facilitar el análisis, se utilizará $e_o(t)$ para representar el voltaje del capacitor. Por lo tanto:

$$V_C(t)=e_o(t)$$

De esta manera, todas las ecuaciones posteriores utilizarán $e_o(t)$ como voltaje de salida.

Debido a que los elementos están conectados en serie, la misma corriente $i(t)$ circula por la resistencia, el inductor y el capacitor.

El objetivo es obtener la ecuación diferencial que representa el comportamiento del circuito y posteriormente obtener su función de transferencia mediante la transformada de Laplace.

---

# 2. Ecuaciones de los Componentes

## 2.1 Resistencia

La resistencia es el elemento que se opone al paso de la corriente eléctrica.

El voltaje en la resistencia está dado por la Ley de Ohm:

$$v_R(t)=Ri(t)$$

donde $R$ representa la resistencia e $i(t)$ representa la corriente que circula por el circuito.

---

## 2.2 Inductor

El inductor almacena energía en forma de campo magnético.

El voltaje en el inductor está dado por:

$$v_L(t)=L\frac{di(t)}{dt}$$

donde $L$ representa la inductancia.

Esta ecuación relaciona el voltaje del inductor con la variación de la corriente respecto al tiempo.

---

## 2.3 Capacitor

El capacitor almacena energía en forma de campo eléctrico.

Normalmente, el voltaje del capacitor se representa mediante $V_C(t)$.

Para este análisis se define el voltaje de salida como $e_o(t)$, por lo que:

$$V_C(t)=e_o(t)$$

La ecuación del capacitor es:

$$e_o(t)=\frac{q(t)}{C}$$

donde $q(t)$ representa la carga eléctrica y $C$ representa la capacitancia.

La corriente del capacitor está relacionada con el voltaje mediante:

$$i(t)=C\frac{de_o(t)}{dt}$$

Por lo tanto, la corriente depende de la variación del voltaje de salida respecto al tiempo.

---

# 3. Ley de Kirchhoff

Para obtener la ecuación del circuito se aplica la Ley de Kirchhoff de Voltajes.

Esta ley establece que la suma de las caídas de voltaje en el circuito es igual al voltaje de entrada.

Por lo tanto:

$$e_i(t)=v_R(t)+v_L(t)+e_o(t)$$

Sustituyendo las ecuaciones de cada componente:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Esta expresión representa el comportamiento del circuito RLC en el dominio del tiempo.

---

# 4. Obtención de la Ecuación Diferencial

Partimos de la ecuación obtenida mediante la Ley de Kirchhoff:

$$e_i(t)=Ri(t)+L\frac{di(t)}{dt}+e_o(t)$$

Para el capacitor sabemos que:

$$i(t)=C\frac{de_o(t)}{dt}$$

Derivando esta expresión:

$$\frac{di(t)}{dt}=C\frac{d^2e_o(t)}{dt^2}$$

Sustituyendo la corriente y su derivada en la ecuación de Kirchhoff:

$$e_i(t)=RC\frac{de_o(t)}{dt}+LC\frac{d^2e_o(t)}{dt^2}+e_o(t)$$

Ordenando los términos:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Por lo tanto, la ecuación diferencial del sistema es:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Esta ecuación diferencial describe la relación entre el voltaje de entrada y el voltaje de salida del circuito RLC.

---

# 5. Condiciones Iniciales

Para aplicar correctamente la transformada de Laplace se deben considerar las condiciones iniciales del sistema.

El voltaje inicial del capacitor, que corresponde al voltaje de salida, se representa mediante:

$$e_o(0)$$

La corriente inicial del circuito se representa mediante:

$$i(0)$$

Como:

$$i(t)=C\frac{de_o(t)}{dt}$$

entonces:

$$i(0)=Ce_o'(0)$$

Para obtener la función de transferencia se consideran condiciones iniciales cero:

$$e_o(0)=0$$

$$e_o'(0)=0$$

---

# 6. Transformada de Laplace

La transformada de Laplace permite transformar la ecuación diferencial del dominio del tiempo al dominio de la variable $s$.

Partimos de la ecuación diferencial:

$$LC\frac{d^2e_o(t)}{dt^2}+RC\frac{de_o(t)}{dt}+e_o(t)=e_i(t)$$

Las transformadas utilizadas son:

$$L\{\frac{de_o(t)}{dt}\}=sE_o(s)-e_o(0)$$

$$L\{\frac{d^2e_o(t)}{dt^2}\}=s^2E_o(s)-se_o(0)-e_o'(0)$$

Además:

$$L\{e_o(t)\}=E_o(s)$$

y:

$$L\{e_i(t)\}=E_i(s)$$

Aplicando la transformada de Laplace a la ecuación diferencial:

$$LC[s^2E_o(s)-se_o(0)-e_o'(0)]+RC[sE_o(s)-e_o(0)]+E_o(s)=E_i(s)$$

Considerando las condiciones iniciales cero:

$$e_o(0)=0$$

$$e_o'(0)=0$$

La expresión se simplifica a:

$$LCs^2E_o(s)+RCsE_o(s)+E_o(s)=E_i(s)$$

Factorizando $E_o(s)$:

$$E_o(s)[LCs^2+RCs+1]=E_i(s)$$

---

# 7. Función de Transferencia

Despejando $E_o(s)$:

$$E_o(s)=\frac{E_i(s)}{LCs^2+RCs+1}$$

La función de transferencia se define como la relación entre la salida y la entrada en el dominio de Laplace:

$$G(s)=\frac{E_o(s)}{E_i(s)}$$

Por lo tanto, la función de transferencia del circuito RLC en serie es:

$$G(s)=\frac{1}{LCs^2+RCs+1}$$

Esta expresión representa matemáticamente la relación entre el voltaje de salida $E_o(s)$ y el voltaje de entrada $E_i(s)$.

---

# 8. Conclusiones

El análisis del circuito RLC en serie permitió obtener su modelo matemático a partir de las ecuaciones correspondientes a la resistencia, el inductor y el capacitor.

Para realizar el análisis se estableció que el voltaje del capacitor $V_C(t)$ corresponde al voltaje de salida $e_o(t)$. Por esta razón, se utiliza $e_o(t)$ en las ecuaciones del sistema.

Mediante la Ley de Kirchhoff de Voltajes se obtuvo una ecuación diferencial de segundo orden que relaciona el voltaje de entrada $e_i(t)$ con el voltaje de salida $e_o(t)$.

Posteriormente, se aplicó la transformada de Laplace considerando condiciones iniciales cero, lo que permitió transformar la ecuación diferencial en una expresión algebraica en el dominio de $s$.

Finalmente, se obtuvo la función de transferencia:

$$G(s)=\frac{E_o(s)}{E_i(s)}=\frac{1}{LCs^2+RCs+1}$$

Con esto se obtiene el modelo matemático del circuito RLC en serie y la relación entre su voltaje de entrada y su voltaje de salida.
