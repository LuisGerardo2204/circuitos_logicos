---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
    language: es
kernelspec:
  display_name: Octave
  language: Octave
  name: Octave
---

# Compuertas Lógicas en VHDL

El objetivo de esta práctica es aprender a utilizar las compuertas lógicas básicas en VHDL. Las compuertas lógicas son el elemento básico de los sistemas digitales, en la {numref}`tabla5` se resume el comportamiento o salida de la compuertas básicas en funcion de sus entradas.


```{list-table} Tabla de verdad de las compuertas básicas
:header-rows: 1
:align: left
:name: tabla5

* - A
  - B
  - AND
  - OR
  - NAND
  - NOR
  - XOR
  - XNOR
* - **0**
  - **0**
  - 0
  - 0 
  - 1
  - 1
  - 0
  - 1
* - **0**
  - **1**
  - 0
  - 1 
  - 1
  - 0
  - 1
  - 0
* - **1**
  - **0**
  - 0
  - 1 
  - 1
  - 0
  - 1
  - 0
* - **1**
  - **1**
  - 1
  - 1 
  - 0
  - 0
  - 0
  - 1
```
En la figura {numref}`compuertas` se muestra el circuito lógico para la prueba de múltiples compuertas lógicas. el código en VHDL para simular su comportamiento se muestra abajo.



# Práctica de compuertas en VHDL

```{figure} /images/diagrama3.png
:height: 450px
:name: compuertas
Compuertas básicas, funciones almacenadas en un arreglo.
```



``` VHDL
--------------------------------
--Compuertas básicas en VHDL
-------------------------------
library IEEE;
use IEEE.std_logic_1164.all; -- Librería para variables lógicas estandard

entity compuertas_basicas is
   port(
   X,Y :in std_logic; -- Entradas simples
   F :out std_logic_vector(8 downto 1) -- Salidas almacenadas en un arreglo
   );
end compuertas_basicas;

architecture arq of compuertas_basicas is

begin 

F(1) <= NOT X; -- Compuerta not
F(2) <= NOT Y; -- Compuerta not
F(3) <= X AND Y; -- Compuerta AND
F(4) <= X NAND Y; -- Compuerta NAND
F(5) <= X OR Y; -- Compuerta OR
F(6) <= X NOR Y; -- Compuerta NOR
F(7) <= X XNOR Y; -- Compuerta XOR
F(8) <= X XOR Y; -- Compuerta XNOR

end arq; 

```



 


