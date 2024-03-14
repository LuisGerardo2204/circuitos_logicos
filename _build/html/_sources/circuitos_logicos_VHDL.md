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

# Breve introducción a VHDL

En cierta forma VHDL utiliza una sintaxis poco usual para describir los circuitos lógicos.
La razón principal de ello es que VHDL se pensó originalmente como un lenguaje para la
documentación y simulación de circuitos, no para describir los circuitos para la síntesis. Este
apéndice no pretende ser un manual completo de VHDL. Si bien estudiamos casi todas sus funciones
útiles en la síntesis de circuitos lógicos, no analizamos ninguna de las que sólo sirven para
su simulación o para otros propósitos. Aun cuando las funciones omitidas no son necesarias
para ninguno de los ejemplos expuestos en la obra, un lector que desee aprender más del uso de
VHDL puede remitirse a libros especializados

```VHDL
--------------------------------------------------------------------
--- Ejemplo de una arquitectura en VHDL
--------------------------------------------------------------------

library IEEE;
use IEEE.std_logic_1164.all;
use IEEE.numeric_std.all;
-- use IEEE.std_logic_unsigned.all;

entity decodificador is
    Port ( entradas : in STD_LOGIC_VECTOR (2 downto 0);
           salidas : out STD_LOGIC_VECTOR (2 downto 0)
);
end decodificador;

architecture Behavioral of decodificador is

begin
with entradas select
      salidas<= "000" when "000",
           	    "010" when "001",
                "010" when "010",
                "100" when "011",
                "010" when "100",
                "100" when "101",
                "100" when "110",
                "110" when "111",
                "000" when others;
end Behavioral;
```
