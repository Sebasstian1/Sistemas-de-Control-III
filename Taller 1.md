%% =========================================================
% SISTEMAS DE CONTROL III
% EJERCICIO 1 - CIRCUITO RLC SERIE
%
% OBJETIVO:
% Obtener la ecuacion diferencial y la funcion de
% transferencia del circuito RLC mostrado.
%
% ENTRADA:
%       ei(t) -> Voltaje de entrada
%
% SALIDA:
%       eo(t) -> Voltaje de salida medido en el capacitor
%
% ELEMENTOS:
%       R -> Resistencia
%       L -> Inductancia
%       C -> Capacitancia
%% =========================================================

clc;
clear;
close all;


%% =========================================================
% PASO 1: DEFINICION DE LAS VARIABLES
% =========================================================
%
% En este paso se definen las variables simbolicas que
% utilizaremos para realizar el desarrollo matematico.
%
% R representa la resistencia en ohmios.
% L representa la inductancia en henrios.
% C representa la capacitancia en faradios.
% t representa el tiempo.
% s representa la variable compleja de Laplace.
%
% ei(t) representa la señal de entrada.
% eo(t) representa la señal de salida.
% i(t) representa la corriente que circula por el circuito.

syms R L C t s
syms ei(t) eo(t) i(t)


fprintf('================================================\n');
fprintf('          SISTEMAS DE CONTROL III\n');
fprintf('             EJERCICIO 1 - RLC\n');
fprintf('================================================\n\n');


%% =========================================================
% PASO 2: IDENTIFICACION DEL SISTEMA
% =========================================================
%
% El circuito esta formado por una resistencia R,
% un inductor L y un capacitor C conectados en serie.
%
% Al estar conectados en serie, la misma corriente i(t)
% circula por los tres elementos.
%
% La entrada del sistema es ei(t).
% La salida del sistema es eo(t), que corresponde al
% voltaje medido en el capacitor.

fprintf('PASO 2: IDENTIFICACION DEL SISTEMA\n\n');

fprintf('Entrada del sistema: ei(t)\n');
fprintf('Salida del sistema:  eo(t)\n');
fprintf('Configuracion: R, L y C conectados en serie.\n');
fprintf('La corriente i(t) es la misma en los tres elementos.\n\n');


%% =========================================================
% PASO 3: LEY DE VOLTAJES DE KIRCHHOFF
% =========================================================
%
% Debido a que tenemos una sola malla, aplicamos la
% Ley de Voltajes de Kirchhoff.
%
% Esta ley establece que la suma de las caidas de tension
% en los elementos del circuito es igual a la tension
% aplicada por la fuente.
%
% Por lo tanto:
%
% ei(t) = eR(t) + eL(t) + eC(t)
%
% Como la salida se encuentra en el capacitor:
%
% eC(t) = eo(t)
%
% Entonces:
%
% ei(t) = eR(t) + eL(t) + eo(t)

fprintf('PASO 3: LEY DE VOLTAJES DE KIRCHHOFF\n\n');

fprintf('Para la malla del circuito se tiene:\n\n');
fprintf('ei(t) = eR(t) + eL(t) + eC(t)\n\n');

fprintf('Como la salida esta medida en el capacitor:\n\n');
fprintf('eC(t) = eo(t)\n\n');

fprintf('Por lo tanto:\n\n');
fprintf('ei(t) = eR(t) + eL(t) + eo(t)\n\n');


%% =========================================================
% PASO 4: ECUACION DE LA RESISTENCIA
% =========================================================
%
% Para la resistencia utilizamos la Ley de Ohm:
%
% eR(t) = R*i(t)
%
% Donde:
% R = resistencia
% i(t) = corriente que circula por el circuito

fprintf('PASO 4: ECUACION DE LA RESISTENCIA\n\n');

fprintf('Aplicando la Ley de Ohm:\n\n');
fprintf('eR(t) = R*i(t)\n\n');

eR = R*i(t);

disp('La tension en la resistencia es:');
disp(eR);
fprintf('\n');


%% =========================================================
% PASO 5: ECUACION DEL INDUCTOR
% =========================================================
%
% Para el inductor utilizamos la relacion:
%
% eL(t) = L*di(t)/dt
%
% Esto significa que el voltaje del inductor depende
% de la variacion de la corriente con respecto al tiempo.

fprintf('PASO 5: ECUACION DEL INDUCTOR\n\n');

fprintf('La tension en el inductor es:\n\n');
fprintf('eL(t) = L*di(t)/dt\n\n');

eL = L*diff(i(t),t);

disp('La tension en el inductor es:');
disp(eL);
fprintf('\n');


%% =========================================================
% PASO 6: ECUACION DEL CAPACITOR
% =========================================================
%
% Para el capacitor utilizamos la relacion:
%
% i(t) = C*deC(t)/dt
%
% Como la tension del capacitor es igual a la salida:
%
% eC(t) = eo(t)
%
% Entonces:
%
% i(t) = C*deo(t)/dt

fprintf('PASO 6: ECUACION DEL CAPACITOR\n\n');

fprintf('La relacion corriente-voltaje del capacitor es:\n\n');
fprintf('i(t) = C*deo(t)/dt\n\n');

corriente_capacitor = C*diff(eo(t),t);

disp('Por lo tanto, la corriente es:');
disp(corriente_capacitor);
fprintf('\n');


%% =========================================================
% PASO 7: DERIVADA DE LA CORRIENTE
% =========================================================
%
% En la ecuacion del inductor necesitamos conocer:
%
% di(t)/dt
%
% Partimos de:
%
% i(t) = C*deo(t)/dt
%
% Derivamos ambos lados respecto al tiempo:
%
% di(t)/dt = C*d2eo(t)/dt2

fprintf('PASO 7: DERIVADA DE LA CORRIENTE\n\n');

fprintf('Partimos de:\n\n');
fprintf('i(t) = C*deo(t)/dt\n\n');

fprintf('Derivando ambos lados respecto al tiempo:\n\n');
fprintf('di(t)/dt = C*d2eo(t)/dt2\n\n');

derivada_corriente = diff(corriente_capacitor,t);

disp('La derivada de la corriente es:');
disp(derivada_corriente);
fprintf('\n');


%% =========================================================
% PASO 8: SUSTITUCION EN LA ECUACION DE KIRCHHOFF
% =========================================================
%
% La ecuacion obtenida mediante Kirchhoff es:
%
% ei(t) = eR(t) + eL(t) + eo(t)
%
% Sabemos que:
%
% eR(t) = R*i(t)
%
% eL(t) = L*di(t)/dt
%
% i(t) = C*deo(t)/dt
%
% di(t)/dt = C*d2eo(t)/dt2
%
% Sustituimos todas estas expresiones.

fprintf('PASO 8: SUSTITUCION EN LA ECUACION DE KIRCHHOFF\n\n');

fprintf('La ecuacion de Kirchhoff es:\n\n');
fprintf('ei(t) = eR(t) + eL(t) + eo(t)\n\n');

fprintf('Sustituyendo la resistencia y el inductor:\n\n');
fprintf('ei(t) = R*i(t) + L*di(t)/dt + eo(t)\n\n');

fprintf('Ahora sustituimos la corriente del capacitor:\n\n');
fprintf('i(t) = C*deo(t)/dt\n\n');

fprintf('Y su derivada:\n\n');
fprintf('di(t)/dt = C*d2eo(t)/dt2\n\n');


%% =========================================================
% PASO 9: ECUACION DIFERENCIAL
% =========================================================
%
% Al realizar las sustituciones obtenemos:
%
% ei(t) = R*C*deo(t)/dt
%         + L*C*d2eo(t)/dt2
%         + eo(t)
%
% Ordenando los terminos:
%
% L*C*d2eo(t)/dt2
% + R*C*deo(t)/dt
% + eo(t)
% = ei(t)

fprintf('PASO 9: OBTENCION DE LA ECUACION DIFERENCIAL\n\n');

fprintf('Despues de realizar las sustituciones:\n\n');

fprintf('ei(t) = R*C*deo(t)/dt + L*C*d2eo(t)/dt2 + eo(t)\n\n');

fprintf('Ordenando los terminos:\n\n');

fprintf('L*C*d2eo(t)/dt2 + R*C*deo(t)/dt + eo(t) = ei(t)\n\n');

fprintf('================================================\n');
fprintf('ECUACION DIFERENCIAL FINAL:\n');
fprintf('================================================\n\n');

fprintf('L*C*d2eo(t)/dt2 + R*C*deo(t)/dt + eo(t) = ei(t)\n\n');


%% =========================================================
% PASO 10: TRANSFORMADA DE LAPLACE
% =========================================================
%
% Para obtener la funcion de transferencia transformamos
% la ecuacion diferencial del dominio del tiempo al dominio
% de Laplace.
%
% La ecuacion diferencial es:
%
% L*C*d2eo(t)/dt2 + R*C*deo(t)/dt + eo(t) = ei(t)
%
% Consideramos condiciones iniciales nulas:
%
% eo(0) = 0
%
% deo(0)/dt = 0
%
% De esta manera:
%
% L{deo(t)/dt} = s*Eo(s)
%
% L{d2eo(t)/dt2} = s^2*Eo(s)

fprintf('PASO 10: TRANSFORMADA DE LAPLACE\n\n');

fprintf('Para obtener la funcion de transferencia se consideran\n');
fprintf('condiciones iniciales nulas.\n\n');

fprintf('eo(0) = 0\n');
fprintf('deo(0)/dt = 0\n\n');

fprintf('Aplicando Transformada de Laplace:\n\n');

fprintf('L{deo(t)/dt} = s*Eo(s)\n');
fprintf('L{d2eo(t)/dt2} = s^2*Eo(s)\n\n');


%% =========================================================
% PASO 11: ECUACION EN EL DOMINIO DE LAPLACE
% =========================================================
%
% Aplicando Laplace a:
%
% L*C*d2eo(t)/dt2 + R*C*deo(t)/dt + eo(t) = ei(t)
%
% obtenemos:
%
% L*C*s^2*Eo(s)
% + R*C*s*Eo(s)
% + Eo(s)
% = Ei(s)

fprintf('PASO 11: ECUACION EN EL DOMINIO DE LAPLACE\n\n');

fprintf('La ecuacion transformada es:\n\n');

fprintf('L*C*s^2*Eo(s) + R*C*s*Eo(s) + Eo(s) = Ei(s)\n\n');


%% =========================================================
% PASO 12: FACTORIZACION DE Eo(s)
% =========================================================
%
% En este paso agrupamos todos los terminos que contienen
% Eo(s).
%
% Sacamos Eo(s) como factor comun:
%
% Eo(s)[L*C*s^2 + R*C*s + 1] = Ei(s)

fprintf('PASO 12: FACTORIZACION DE Eo(s)\n\n');

fprintf('Sacamos Eo(s) como factor comun:\n\n');

fprintf('Eo(s)[L*C*s^2 + R*C*s + 1] = Ei(s)\n\n');


%% =========================================================
% PASO 13: OBTENCION DE LA FUNCION DE TRANSFERENCIA
% =========================================================
%
% La funcion de transferencia de un sistema se define como:
%
%              Eo(s)
% G(s) = ----------------
%              Ei(s)
%
% con condiciones iniciales nulas.
%
% Despejando Eo(s)/Ei(s):
%
%              1
% G(s) = ------------------------
%        L*C*s^2 + R*C*s + 1

fprintf('PASO 13: FUNCION DE TRANSFERENCIA\n\n');

fprintf('Por definicion:\n\n');

fprintf('             Eo(s)\n');
fprintf('G(s) = ----------------\n');
fprintf('             Ei(s)\n\n');

fprintf('Despejando se obtiene:\n\n');

fprintf('                 1\n');
fprintf('G(s) = -------------------------\n');
fprintf('       L*C*s^2 + R*C*s + 1\n\n');


%% =========================================================
% PASO 14: REPRESENTACION SIMBOLICA EN MATLAB
% =========================================================
%
% Finalmente representamos la funcion de transferencia
% utilizando variables simbolicas.
%
% La expresion obtenida es:
%
%                 1
% G(s) = -------------------------
%       L*C*s^2 + R*C*s + 1

fprintf('PASO 14: REPRESENTACION SIMBOLICA\n\n');

G = 1/(L*C*s^2 + R*C*s + 1);

fprintf('La funcion de transferencia obtenida es:\n\n');

disp(G);

fprintf('\n');


%% =========================================================
% RESULTADOS FINALES
% =========================================================

fprintf('================================================\n');
fprintf('              RESULTADOS FINALES\n');
fprintf('================================================\n\n');

fprintf('1. ECUACION DIFERENCIAL:\n\n');

fprintf('L*C*d2eo(t)/dt2 + R*C*deo(t)/dt + eo(t) = ei(t)\n\n');

fprintf('2. FUNCION DE TRANSFERENCIA:\n\n');

fprintf('                 1\n');
fprintf('G(s) = -------------------------\n');
fprintf('       L*C*s^2 + R*C*s + 1\n\n');

fprintf('Donde:\n');
fprintf('ei(t) -> Entrada del sistema\n');
fprintf('eo(t) -> Salida del sistema\n\n');

fprintf('================================================\n');
fprintf('             FIN DEL EJERCICIO\n');
fprintf('================================================\n');
