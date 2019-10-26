# Mixer

## Função do bloco

Um mixer, ou misturador, é um circuito utilizado em cadeias de RF (transmissão e recepção) de forma a "misturar" dois sinais, de forma a produzir a soma ou a diferença entre as frequências desses sinais. Na figura abaixo, utiliza-se os sinais em frequẽncais f2 e f, e, após passagem pelo mixer, obtem-se sinais em f-f2 e f+f2.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/goal.png">
</p>

Em cadeias de recepção, utiliza-se um mixer de forma a transportar um sinal de portadora elevada em um sinal ou em banda-base ou para uma frequência intermediária, a última sendo escolhida neste projeto. Dessa forma, geralmente, somente a frequência que é a diferença entre a frequência da portadora e a frequência de um oscilador local (LO), com frequência definida pelo usuário ou pelo projetista, é desejada, de forma que as frequências original, seus harmônicos e a soma deva ser removida com filtragem.

## Seleção do componente

Objetiva-se escolher um mixer para receber o sinal em RF modulado em amplitude (AM) com intervalo de frequências de 108 MHz a 136,9917 MHz utilizando um oscilador local para transportar o sinal para uma frequência intermediária (IF) de 455 kHz.

O mixer escolhido foi o ADE-6+, da Mini-Circuits, já que apresenta um grande intervalo de frequências para sinal RF e do oscilador local; é passivo, de forma a não demandar alimentação; é pequeno, ocupando 44 milímetros quadrados; e com intervalo grande de temperaturas de operação.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/schematic.png">
</p>

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/drawing.png">
</p>

## Descrição dos parâmetros do bloco

Os parâmetros definitivos para a escolha do mixer ADE-6+ foram a frequência de operação; as potências de entrada dos sinais RF e LO; a perda de conversão; o isolamento L-I e L-R; a potência de IP3; a potência P1dB; e as temperaturas de operação.

* **Frequẽncias de operação:** de 0.05 a 250 MHz, cobrindo toda a faixa requisitada no projeto.
* **Potência de entrada do sinal de RF:** -29.4 dBm, escolhida de forma a não gerar componentes significativas de 3º harmônico do sinal.
* **Potência de entrada do sinal do oscilador local:** 7 dBm, de forma a ter uma boa faixa de operação em termos de perda de conversão, isolamento, e VSWR.
* **Corrente de FI:** 40 mA, de forma que o filtro posterior deve suportar tal corrente.
* **Perda de conversão:** 4,3 dB, um valor usual para mixers, que estão depois de vários blocos de amplificação, de forma que interferem muito pouco na figura de ruído do sistema.
* **Isolamento L-I e L-R:** valores que garantem que a frequência de oscilador local seja atenuada e não passe para o sinal de IF ou de RF, o que pode gerar harmônicos indesejados no sinal de IF ou reflexão na cadeia de recepção na faixa de RF, gerando uma componente DC indesejada. O isolamento L-R é de 40 dB e o isolamento L-I, 45 dB.
* **Potência IP3**: 10 dBm, que corresponde a potência teórica de entrada na qual a potência de saída do sinal desejado e do seu 3º harmônico indesejado são iguais. Escolheu-se como potência de entrada do sinal RF -29.4 dBm para termos um valor aproximadamente 40 dB abaixo de IP3, o que garante baixa distorção de 3º harmônico.
* **Potência P1dB**: 1 dBm, o que garante que estamos na região linear do componente.
* **Temperatura de operação:** -40ºC a 85ºC.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/vswr.png">
</p>

## Simulações preliminares

Para ter uma ideia de como será o comportamento no componente, para a faixa de frequências de operação do receptor, tomou-se os valores da perda de conversão, isolamento entre as portas e potência de entrada dos sinais de RF e de LO, bem como os valores de IP3 e P1dB, e simulou-se no software NI AWR um mixer com tais parâmetros. Os gráficos abaixo mostram o espectro do sinal IF da saída do mixer, representando a presença dos produtos de intermodulação e também vendo as frequências em torno da frequẽncia de IF.

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/intermod.png">
</p>

<p align="center">
  <img src="https://github.com/apct-2019/Sampaio/blob/master/images/if.png">
</p>
