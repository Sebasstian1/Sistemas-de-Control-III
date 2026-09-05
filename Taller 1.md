

%% ============================================================
%       SISTEMAS DE CONTROL III - CIRCUITO RLC
%       Circuito RLC en serie
%       Entrada:  ei(t)
%       Salida:   eo(t) - Voltaje en el capacitor
% =============================================================

%% 1. Definición de variables simbólicas

syms R L C t s
syms ei(t) eo(t) i(t)

%% 2. Ecuación del capacitor

% i(t) = C * d(eo)/dt

i_capacitor = C*diff(eo,t);

%% 3. Derivada de la corriente

% di/dt = C * d2(eo)/dt2

di_dt = diff(i_capacitor,t);

%% 4. Voltaje en la resistencia

% eR(t) = R*i(t)

eR = R*i_capacitor;

%% 5. Voltaje en el inductor

% eL(t) = L*di/dt

eL = L*di_dt;

%% 6. Ley de Voltajes de Kirchhoff

% ei(t) = eR(t) + eL(t) + eo(t)

ecuacion = simplify(ei == eR + eL + eo);

disp(' ');
disp('============================================');
disp('      ECUACION DIFERENCIAL DEL SISTEMA');
disp('============================================');

pretty(equationToExpr(ecuacion))


%% 7. Ecuación diferencial desarrollada

ecuacion_diferencial = ...
    L*C*diff(eo,t,2) + ...
    R*C*diff(eo,t) + ...
    eo == ei;

disp(' ');
disp('Ecuacion diferencial:');

pretty(ecuacion_diferencial)


%% 8. Transformada de Laplace

% Condiciones iniciales nulas

% L{d(eo)/dt} = s*Eo(s)
% L{d2(eo)/dt2} = s^2*Eo(s)

Eo = sym('Eo');
Ei = sym('Ei');

ecuacion_laplace = ...
    L*C*s^2*Eo + ...
    R*C*s*Eo + ...
    Eo == Ei;

disp(' ');
disp('============================================');
disp('       ECUACION EN EL DOMINIO DE LAPLACE');
disp('============================================');

pretty(ecuacion_laplace)


%% 9. Despejar Eo(s)

Eo_solucion = solve(ecuacion_laplace,Eo);

disp(' ');
disp('Eo(s) = ');

pretty(Eo_solucion)


%% 10. Funcion de transferencia

% G(s) = Eo(s)/Ei(s)

G = simplify(Eo_solucion/Ei);

disp(' ');
disp('============================================');
disp('             FUNCION DE TRANSFERENCIA');
disp('============================================');

pretty(G)


%% 11. Mostrar la funcion de transferencia

disp(' ');
disp('Resultado final:');

fprintf('\n');
disp('             1');
disp('G(s) = -------------------------');
disp('        L*C*s^2 + R*C*s + 1');
fprintf('\n');


%% 12. Ejemplo numerico

% Valores del circuito
% R = 10 Ohm
% L = 1 H
% C = 0.1 F

R_val = 10;
L_val = 1;
C_val = 0.1;

G_numerica = subs(G,...
    [R L C],...
    [R_val L_val C_val]);

disp('============================================');
disp('          FUNCION DE TRANSFERENCIA');
disp('             CASO NUMERICO');
disp('============================================');

pretty(G_numerica)


%% 13. Convertir a funcion de transferencia de MATLAB

% Numerador y denominador

[num,den] = numden(G_numerica);

num = double(num);
den = double(den);

sys = tf(num,den);

disp(' ');
disp('Funcion de transferencia en MATLAB:');

sys


%% 14. Polos del sistema

polos = pole(sys);

disp(' ');
disp('============================================');
disp('                 POLOS');
disp('============================================');

disp(polos);


%% 15. Respuesta al escalon

figure;

step(sys);

grid on;

title('Respuesta al escalon - Circuito RLC');

xlabel('Tiempo (s)');
ylabel('Voltaje de salida e_o(t)');


%% 16. Diagrama de polos y ceros

figure;

pzmap(sys);

grid on;

title('Diagrama de Polos y Ceros');


%% 17. Informacion del sistema

disp(' ');
disp('============================================');
disp('          INFORMACION DEL SISTEMA');
disp('============================================');

damp(sys)
```
