clc;
clear;
close all;

syms R L C t s
syms ei(t) eo(t) i(t)
syms Ei Eo

% Ecuacion del capacitor
i = C*diff(eo,t);

% Derivada de la corriente
di = diff(i,t);

% Voltaje en la resistencia
eR = R*i;

% Voltaje en el inductor
eL = L*di;

% Ley de Kirchhoff
ecuacion = ei == eR + eL + eo;

% Ecuacion diferencial
ecuacion_diferencial = ...
    L*C*diff(eo,t,2) + ...
    R*C*diff(eo,t) + ...
    eo == ei;

% Ecuacion en el dominio de Laplace
ecuacion_laplace = ...
    L*C*s^2*Eo + ...
    R*C*s*Eo + ...
    Eo == Ei;

% Despejar Eo(s)
Eo_solucion = solve(ecuacion_laplace,Eo);

% Funcion de transferencia
G = simplify(Eo_solucion/Ei);

% Mostrar resultados
disp('Ecuacion de Kirchhoff:')
pretty(ecuacion)

disp('Ecuacion diferencial:')
pretty(ecuacion_diferencial)

disp('Ecuacion en Laplace:')
pretty(ecuacion_laplace)

disp('Eo(s):')
pretty(Eo_solucion)

disp('Funcion de transferencia G(s):')
pretty(G)
