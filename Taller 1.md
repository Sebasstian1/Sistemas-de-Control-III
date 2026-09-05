```latex
\section{Implementación en MATLAB}

Para implementar el procedimiento matemático obtenido anteriormente se utiliza MATLAB, empleando variables simbólicas para representar los elementos del circuito RLC y obtener de forma algebraica la ecuación diferencial y la función de transferencia.

El siguiente programa realiza el procedimiento completo:

\begin{lstlisting}[language=Matlab, caption={Implementación simbólica y numérica del circuito RLC}]
clc;
clear;
close all;

%% =========================================================
% CIRCUITO RLC EN SERIE
% Entrada: ei(t)
% Salida: eo(t) - Voltaje en el capacitor
% ==========================================================

%% 1. Definicion de variables simbolicas

syms R L C t s
syms ei(t) eo(t)
syms Ei Eo

%% 2. Ecuacion del capacitor

% i(t) = C * d(eo)/dt
corriente = C * diff(eo,t);

disp('==============================================');
disp('CORRIENTE DEL CAPACITOR');
disp('==============================================');
pretty(corriente);

%% 3. Derivada de la corriente

% di/dt = C * d2(eo)/dt2
derivada_corriente = diff(corriente,t);

disp('==============================================');
disp('DERIVADA DE LA CORRIENTE');
disp('==============================================');
pretty(derivada_corriente);

%% 4. Voltaje en la resistencia

% eR(t) = R*i(t)
eR = R * corriente;

disp('==============================================');
disp('VOLTAJE EN LA RESISTENCIA');
disp('==============================================');
pretty(eR);

%% 5. Voltaje en el inductor

% eL(t) = L*di/dt
eL = L * derivada_corriente;

disp('==============================================');
disp('VOLTAJE EN EL INDUCTOR');
disp('==============================================');
pretty(eL);

%% 6. Ley de Voltajes de Kirchhoff

% ei(t) = eR(t) + eL(t) + eo(t)

ecuacion_KVL = ei == eR + eL + eo;

disp('==============================================');
disp('LEY DE VOLTAJES DE KIRCHHOFF');
disp('==============================================');
pretty(ecuacion_KVL);

%% 7. Ecuacion diferencial

ecuacion_diferencial = ...
    L*C*diff(eo,t,2) + ...
    R*C*diff(eo,t) + ...
    eo == ei;

disp('==============================================');
disp('ECUACION DIFERENCIAL');
disp('==============================================');
pretty(ecuacion_diferencial);

%% 8. Transformada de Laplace

% Condiciones iniciales nulas:
% eo(0) = 0
% deo/dt(0) = 0

ecuacion_laplace = ...
    L*C*s^2*Eo + ...
    R*C*s*Eo + ...
    Eo == Ei;

disp('==============================================');
disp('ECUACION EN EL DOMINIO DE LAPLACE');
disp('==============================================');
pretty(ecuacion_laplace);

%% 9. Despejar Eo(s)

Eo_solucion = solve(ecuacion_laplace,Eo);

disp('==============================================');
disp('Eo(s)');
disp('==============================================');
pretty(Eo_solucion);

%% 10. Funcion de transferencia

G = simplify(Eo_solucion/Ei);

disp('==============================================');
disp('FUNCION DE TRANSFERENCIA');
disp('==============================================');

pretty(G);

%% =========================================================
% EJEMPLO NUMERICO
% ==========================================================

%% 11. Valores del circuito

R_val = 10;       % Ohm
L_val = 1;        % Henry
C_val = 0.1;      % Farad

disp('==============================================');
disp('VALORES DEL CIRCUITO');
disp('==============================================');

fprintf('R = %.2f Ohm\n',R_val);
fprintf('L = %.2f H\n',L_val);
fprintf('C = %.2f F\n',C_val);

%% 12. Funcion de transferencia numerica

% G(s) = 1/(LC*s^2 + RC*s + 1)

numerador = 1;

denominador = [L_val*C_val ...
               R_val*C_val ...
               1];

G_num = tf(numerador,denominador);

disp('==============================================');
disp('FUNCION DE TRANSFERENCIA NUMERICA');
disp('==============================================');

G_num

%% 13. Polos del sistema

polos = pole(G_num);

disp('==============================================');
disp('POLOS DEL SISTEMA');
disp('==============================================');

disp(polos);

%% 14. Ceros del sistema

ceros = zero(G_num);

disp('==============================================');
disp('CEROS DEL SISTEMA');
disp('==============================================');

disp(ceros);

%% 15. Respuesta al escalon

figure;
step(G_num);

grid on;

title('Respuesta al escalon del circuito RLC');
xlabel('Tiempo (s)');
ylabel('Voltaje de salida e_o(t)');

%% 16. Diagrama de polos y ceros

figure;

pzmap(G_num);

grid on;

title('Diagrama de polos y ceros');

%% 17. Informacion del sistema

disp('==============================================');
disp('INFORMACION DEL SISTEMA');
disp('==============================================');

damp(G_num);
\end{lstlisting}
```

Para que `lstlisting` funcione, agrega esto **antes de `\begin{document}`**:

```latex
\usepackage{listings}
\usepackage{xcolor}

\lstset{
    basicstyle=\ttfamily\small,
    breaklines=true,
    frame=single,
    numbers=left,
    numberstyle=\tiny,
    captionpos=b,
    showstringspaces=false
}
```

Y después de la sección puedes agregar la interpretación de los resultados:

```latex
\subsection{Resultados obtenidos}

A partir de la implementación simbólica se obtiene la ecuación diferencial:

\begin{equation}
LC\frac{d^2e_o(t)}{dt^2}
+
RC\frac{de_o(t)}{dt}
+
e_o(t)
=
e_i(t)
\end{equation}

Al aplicar la transformada de Laplace considerando condiciones iniciales nulas, se obtiene:

\begin{equation}
LCs^2E_o(s)+RCsE_o(s)+E_o(s)=E_i(s)
\end{equation}

Despejando la relación entre la salida y la entrada:

\begin{equation}
E_o(s)
=
\frac{E_i(s)}
{LCs^2+RCs+1}
\end{equation}

Por lo tanto, la función de transferencia del circuito RLC es:

\begin{equation}
G(s)
=
\frac{E_o(s)}{E_i(s)}
=
\frac{1}
{LCs^2+RCs+1}
\end{equation}
```

Con los valores utilizados en el programa:

```latex
\begin{equation}
R=10\,\Omega,\qquad
L=1\,H,\qquad
C=0.1\,F
\end{equation}
```

la función de transferencia numérica resulta:

```latex
\begin{equation}
G(s)
=
\frac{1}
{0.1s^2+s+1}
\end{equation}
```

También puede expresarse normalizando el denominador:

```latex
\begin{equation}
G(s)
=
\frac{10}
{s^2+10s+10}
\end{equation}
```
