# Mixer

Objetiva-se escolher um mixer para receber o sinal em RF com intervalo de frequências de 108 MHz a 136,9917 MHz utilizando um oscilador local para colocar o sinal em uma frequência intermediária (FI) de 455 kHz.

O objetivo do mixer é deslocar a frequência do sinal que chega da antena, de forma a mudar a frequência da portadora do sinal. As frequências obtidas na saída do mixer devem ser, prioritariamente, a soma e a diferença das frequência da portadora do sinal RF e do oscilador local (prioritariamente pois há também geração de harmônicos indesejados). Posterior filtragem na frequência de interesse, que é a diferença, é utilizada para obter o sinal na frequência FI.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/goal.png">
</p>

O mixer escolhido foi o ADE-12MH, da Mini-Circuits, já que apresenta um grande intervalo para frequência do sinal RF e do oscilador local; é passivo, de forma a não demandar alimentação; é pequeno, ocupando aproximadamente 44 milímetros quadrado; e com intervalo grande de temperaturas de operação.

* Potência de entrada do sinal de RF: 10 dBm
* Potência de entrada do sinal do oscilador local: 13 dBm
* Corrente de FI: 40 mA
* Perda de conversão: 6,3 dB

A potência de entrada máxima é de 23 dBm, porém o valor de 10 dBm foi escolhido porque o IP3 do componente é 22 dBm (típico). Assim, um valor 12 dB abaixo do IP3 garante baixa distorção do terceiro harmônico.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/schematic.png">
</p>

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/drawing.png">
</p>

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/vswr.png">
</p>
