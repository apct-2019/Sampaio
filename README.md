# Mixer

## Função do bloco

Um mixer, ou misturador, é um circuito utilizado em cadeias de RF (transmissão e recepção) de forma a "misturar" dois sinais, de forma a produzir a soma ou a diferença entre as frequências desses sinais.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/goal.png">
</p>

Em cadeias de recepção, utiliza-se um mixer de forma a transportar um sinal de portadora elevada em um sinal ou em banda-base ou para uma frequência intermediária, a última sendo escolhida neste projeto. Dessa forma, geralmente, somente a frequência que é a diferença entre a frequência da portadora e a frequência de um oscilador local (LO), com frequência definida pelo usuário ou pelo projetista, é desejada, de forma que as frequências original, seus harmônicos e a soma deva ser removida com filtragem.

## Seleção do componente

Objetiva-se escolher um mixer para receber o sinal em RF modulado em amplitude (AM) com intervalo de frequências de 108 MHz a 136,9917 MHz utilizando um oscilador local para transportar o sinal para uma frequência intermediária (FI) de 455 kHz.

O mixer escolhido foi o ADE-12MH, da Mini-Circuits, já que apresenta um grande intervalo de frequências para sinal RF e do oscilador local; é passivo, de forma a não demandar alimentação; é pequeno, ocupando aproximadamente 44 milímetros quadrado; e com intervalo grande de temperaturas de operação.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/schematic.png">
</p>

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/drawing.png">
</p>

## Descrição dos parâmetros do bloco

Os parâmetros definitivos para a escolha do mixer ADE-12MH foram a frequência de operação; as potências de entrada dos sinais RF e LO; a perda de conversão; o isolamento L-I e L-R; a potência de IP3; e as temperaturas de operação.

* **Frequẽncias de operação:** de 10 a 1200 MHz, cobrindo toda a faixa requisitada no projeto.
* **Potência de entrada do sinal de RF:** 10 dBm, escolhido de forma a não gerar componentes significativas de 3º harmônico do sinal.
* **Potência de entrada do sinal do oscilador local:** 13 dBm, de forma a ter uma boa faixa de operação em termos de perda de conversão, isolamento, e VSWR.
* **Corrente de FI** 40 mA, de forma que o filtro posterior deve suportar tal corrente.
* **Perda de conversão:** 6,3 dB, um valor usual para mixers, que estão depois de vários blocos de amplificação, de forma que interferem muito pouco na figura de ruído do sistema.
* **Isolamento L-I e L-R:** valores que garantem que a frequência de oscilador local seja atenuada e não passe para o sinal de IF ou de RF, o que pode gerar harmônicos indesejados no sinal de IF ou reflexão na cadeia de recepção na faixa de RF, gerando uma componente DC indesejada. O isolamento L-R é de 45 dB e o isolamento L-I, 42 dB.
* **Potência IP3**: 22 dBm, que corresponde a potência teórica de entrada na qual a potência de saída do sinal desejado e do seu 3º harmônico indesejado são iguais. Escolheu-se como potência de entrada do sinal RF 10 dBm para termos um valor 12 dB abaixo de IP3, o que garante baixa distorção de 3º harmônico.
* **Temperatura de operação:** -40ºC a 85ºC.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/vswr.png">
</p>
