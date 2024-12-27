# Árvore de Natal com Leds


### Nome do Projeto: Controle de Efeitos de LEDs de uma arvore de natal  no NODEMCU

### Descrição: 

Este programa permite controlar cinco saídas digitais (LEDs) conectadas ao NodeMCU (ESP8266) via uma interface web, onde é possível selecionar efeitos de iluminação e ativar/desativar uma melodia de Natal tocada em um buzzer.

<img src="/controle.jpg" width="50%" />

A interface possui botões que indicam o efeito ativo mudando de cor, e uma mensagem no rodapé exibe o efeito atual.


 ### Hardware Utilizado:
 
 - NodeMCU (ESP8266) V 1
 - LEDs conectados nas portas D5, D1, D2, D6 e D4
 - LED embutido na porta D0
 - Buzzer conectado na porta D7

 ### Funcionamento:
 
- Conecta-se a uma rede Wi-Fi com SSID e senha fornecidos.
- Configura IP fixo e inicializa um servidor web na porta 80.
- Exibe uma página de controle com botões de seleção de efeitos para os LEDs e controle de som.
- Quando um efeito é selecionado, o botão correspondente muda de cor para indicar o efeito ativo.
- O som pode ser ligado ou desligado por um botão, e uma melodia de Natal é tocada para efeitos específicos.

### Configurações de Rede:

Dever ser confifurado no código e enciado novamente para o microcontrolador

 - SSID: ************
 - Senha: ***********
 - IP Fixo: 99.99.99.99
 - Gateway: 99.99.99.1
 - Subnet Mask: 255.255.255.0
 
 ### Dependências:
 
 - ESP8266WiFi.h: Para conexão Wi-Fi com o ESP8266.
 - ESP8266WebServer.h: Para inicializar e gerenciar o servidor web.

 Notas:
 
 - Certifique-se de que as portas GPIO selecionadas estão conectadas aos LEDs ou dispositivos adequados.
 - Este código pode ser expandido ou adaptado para controlar outros dispositivos através das saídas digitais.
 
### Tabela de GPIOs 

| Pino (D) | GPIO Correspondente  |
|----------|----------------------|
| D5       | GPIO14               |
| D1       | GPIO5                |
| D2       | GPIO4                |
| D6       | GPIO12               |
| D4       | GPIO2                |
| D0       | GPIO16 (LED embutido)|
| D7       | GPIO13 (Buzzer)      |

<img src="/pinout.jpg" width="50%" />

### Conexão do buzzer

- Conecte o pino positivo (VCC) do buzzer ao pino D7 do NodeMCU (GPIO13).
- Conecte o pino negativo (GND) do buzzer ao GND do NodeMCU.

### Conexão do Leds

Para controlar 10 LEDs usando um driver com transistores,

#### Materiais Necessários

-10 LEDs
-10 resistores (geralmente de 220Ω a 330Ω, dependendo da tensão dos LEDs)
-10 transistores NPN (como o 2N2222 ou BC547) - 1 para cada LED, ou um único transistor MOSFET se todos os LEDs ligarem juntos
-Fonte de alimentação (adequada para os LEDs, geralmente 5V)
-Microcontrolador (como o NodeMCU, Arduino, etc.)

#### Diagrama Básico de Conexão para ligar um LED

<img src="/circuito.jpg" width="50%" />

#### Diagrama Básico de Conexão para ligar varios LEDs

Passo 1: Conexão dos LEDs e Resistores

- Conecte um resistor em série com o anodo (perna positiva) de cada LED.
- Conecte o cátodo (perna negativa) de cada LED ao coletor do transistor NPN correspondente.

Passo 2: Conexão dos Transistores

- Emissor de cada transistor NPN deve ser conectado ao GND da fonte de alimentação.
- Conecte a base de cada transistor a um pino de controle do microcontrolador (como o NodeMCU) através de um resistor (geralmente entre 220Ω a 1kΩ).
- Ligue a alimentação positiva da fonte (5V) ao outro terminal do resistor em série com cada LED.


#### Explicação do Funcionamento

Quando o microcontrolador envia um sinal HIGH para a base do transistor (corrente suficiente para saturar o transistor), o transistor se torna condutor entre o coletor e o emissor, fechando o circuito e ligando o LED. Quando o sinal da base é LOW, o transistor não conduz e o LED permanece apagado.

### Descrição dos Efeitos

* Efeito 1 - Sequencial Ascendente: Liga cada LED um após o outro, de forma ascendente, e depois desliga.
* Efeito 2 - Sequencial Descendente: Liga cada LED um após o outro, mas de forma descendente, e depois desliga.
* Efeito 3 - Todos Ligam e Desligam: Liga todos os LEDs simultaneamente, espera um tempo, e então desliga todos ao mesmo tempo.
* Efeito 4 - Piscar Alternado: Cada LED pisca rapidamente um de cada vez.
* Efeito 5 - Todos Ligam e Desligam Lentamente: Liga todos os LEDs, espera um tempo mais longo, e depois desliga todos juntos.
* Efeito 5 - Leds Amarelos e Azul  Piscam.
