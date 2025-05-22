# O que é Tasmota?

O Tasmota é um firmware de código aberto para dispositivos baseados nos chipsets Espressif ESP8266, ESP32, ESP32-S ou ESP32-C3, criado e mantido por Theo Arends. Ele começou como uma maneira simples de hackear um Sonoff Basic (um dos primeiros dispositivos de casa inteligente baratos e acessíveis no mercado) vinculado à nuvem, transformando-o em um dispositivo controlado localmente. Desde então, evoluiu para um ecossistema completo para praticamente qualquer dispositivo baseado em ESP.

Este tutorial busca ensinar de forma simples e direta comoe instalar e configurar o Tasmota, assim como mostrar os passos para a integração com o Home Assistant, permitindo que você use livremente seus dispositivos ESP para personalizar suas automações residenciais. Utilizaremos um ESP32 neste tutorial, mas as etapas fornecidas também devem funcionar para configurar o Tasmota em dispositivos ESP82XX.

---

* Links para diferentes repositórios do mesmo tema e hospedados no GitHub.

## Repositórios

1. **Home Assistant, Tasmota e MQTT**
   - Repositório: [HomeAssistant-Tasmota-MQTT](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT)

2. **Placa 4in/4out com Tasmota**
   - Repositório: [Tasmota - Placa 4in/4out](https://github.com/Epaminondaslage/Tasmota/tree/main/Placa_4in_4out)
     
3. **TASMOTA para Ai-Thinker Camera (ESP32-CAM)**
   - Repositório: [Tasmota - ESP 32 CAM ](https://github.com/Epaminondaslage/ESP-32-CAM)
     
4. **TASMOTA para a placa KC868-A16**
   - Repositório: [Tasmota KC868-A16 ](https://github.com/Epaminondaslage/Tasmota/blob/main/KC868-A16/README.md)
---

## Principais características do Tasmota

1. **Compatibilidade ampla**:
   - Funciona com diversos dispositivos inteligentes, como lâmpadas, interruptores, sensores e tomadas, desde que utilizem ESP8266 ou ESP32.

2. **Flexibilidade de integração**:
   - Integra-se com diversas plataformas de automação, como:
     - **Home Assistant**
     - **openHAB**
     - **Domoticz**
     - **Node-RED**

3. **Protocolos suportados**:
   - Suporte ao protocolo **MQTT** para comunicação com servidores e sistemas IoT.
   - Controle local por meio de **HTTP** e comandos enviados via interface web.

4. **Interface web integrada**:
   - Permite acessar e controlar o dispositivo diretamente via navegador, configurando funções e monitorando o status.

5. **Configuração por GPIO**:
   - Permite usar os pinos GPIO do dispositivo para conectar sensores, relés, LEDs e outros componentes.

6. **Sem dependência de nuvem**:
   - O Tasmota funciona localmente, sem necessidade de enviar dados para servidores externos, garantindo mais privacidade e segurança.

7. **Atualizações OTA (Over-The-Air)**:
   - Permite atualizar o firmware sem fio, facilitando manutenção e aprimoramentos.

8. **Comunidade ativa**:
   - Por ser um projeto de código aberto, conta com uma comunidade vibrante que contribui com desenvolvimento, documentação e suporte.

## Exemplos de usos
- Controlar a iluminação residencial.
- Automatizar cortinas, portas ou janelas.
- Monitorar sensores de temperatura, umidade ou movimento.
- Gerenciar dispositivos elétricos, como ventiladores ou aquecedores.



# Instruções de Instalação

Os passos apresentados a seguir foram retirados do site oficial do Tasmota: [Tasmota - Getting Started](https://tasmota.github.io/docs/Getting-Started/).

## Software Necessário

### Firmware Binário do Tasmota

Neste tutorial, instalaremos a versão básica do Tasmota para ESP32 usando o Instalador Web, então você não precisará baixar nenhum arquivo ou software para segui-lo. No entanto, caso escolha outro método de instalação, você pode precisar baixar um arquivo binário de firmware do Tasmota (.bin). Se você não tem certeza de qual binário é o certo para você, comece com o **tasmota.bin** ou consulte a [tabela de compilações](https://tasmota.github.io/docs/Firmware-Builds/) para ver quais recursos você precisa. Os binários poder ser obtidos no servidor OTA oficial do Tasmota ([ESP8266](http://ota.tasmota.com/tasmota/release/) e [ESP32](http://ota.tasmota.com/tasmota32/release/)).

### Ferramenta de Flash

O Tasmota oferece 4 ferramentas para a instalação. Usaremos o **Tasmota Web Installer**, pois ele é compatível com ESP82XX e ESP32 e não requer nenhum download ou instalação de software.

- [Tasmota Web Installer](https://tasmota.github.io/install/) - instale o Tasmota usando um navegador baseado no Chrome para ESP82XX e ESP32
- [Tasmotizer](https://github.com/tasmota/tasmotizer) - ferramenta de flash e download de firmware apenas para ESP82XX. (Windows, Linux ou Mac)
- [ESP-Flasher](https://github.com/Jason2866/ESP_Flasher) - ferramenta gráfica para flash baseada no esptool.py para ESP82XX e ESP32. (Windows, Linux ou Mac)
- [Esptool.py](https://github.com/espressif/esptool) - a ferramenta de flash oficial da Espressif para ESP82XX e ESP32. (Requer Python)

## Tasmota Web Installer

Com o Instalador Web do Tasmota, você pode fazer o flash do Tasmota diretamente do seu navegador da web. Você só precisa conectar o dispositivo ESP ao seu computador usando USB ou um adaptador serial para USB (certifique-se que o cabo utilizado suporta transporte de dados!), selecionar a variante de firmware adequada para o seu dispositivo e clicar no botão **CONNECT**. Ele solicitará a porta correta onde o dispositivo está localizado e iniciará o processo de instalação.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/00.png)

Clique em install Tasmota.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/01.png)

Clique em NEXT.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/02.png)

Prossiga com a instalação.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/03.png)

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/04.png)

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/05.png)

Configure o ponto de acesso WIFI.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/06.png)

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/07.png)

Clique em Visit Device para abrir uma nova guia com a interface Web do ESP configurado.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/08.png)

# Interface Web

A interface de usuário web do Tasmota é uma maneira prática de controlar e gerenciar o seu dispositivo com Tasmota. Para acessá-la, use o endereço IP do seu dispositivo no seu navegador web favorito. Por padrão, a interface começa no modo administrador não protegido, que permite acesso completo ao seu dispositivo para qualquer pessoa com acesso a esse IP.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/09.png)

A interface possui 4 opções de menu:

- **Configuração**: O menu de configuração permite que você configure tudo, desde componentes até Wi-Fi, e oferece a opção de fazer backup e restaurar a configuração em um local seguro.
- **Informações**: Exibe uma única página carregada com informações sobre o dispositivo, incluindo: versão atual do Tasmota, dados do ponto de acesso Wi-Fi, dados do host MQTT e muito mais.
- **Atualização de Firmware**: Um menu fácil de usar para iniciar uma atualização de firmware a partir de um arquivo .bin carregado ou de um servidor OTA.
- **Console**: Acesso ao terminal do Tasmota. Emita comandos ou siga o fluxo de informações.

## Configuração

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/10.png)

### Configure Module

Esta janela serve para alterar a configuração do dispositivo ESP, customizando=a como desejado; Para proporcionar o acionamento de um relé, configuramos o GPIO associado para funcionar como relé, como mostrado abaixo.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/11.png)

O ESP32 possui um sensor de efeito Hall embutido que detecta mudanças no campo magnético ao seu redor. Ele está localizado atrás da tampa de metal do módulo e conectado aos pinos GPIO36 e GPIO39. Para habilita-lo, faça a seguinte alteração na configuração do módulo:

- GPIO36 como HallEffect 1
- GPIO39 como HallEffect 2

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/12.png)

Este relé e sensor serão utilizados para demonstração no restante do tutorial. Clique em salvar e espere o dispositivo reiniciar.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/13.png)

Uma vez reiniciado, podemos ver as alterações feitas na tela inicial, que agora mostra o valor do sensor de efeito hall e um botão para acionamento do relé.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/14.png)

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/15.png)

### Configure MQTT

Conecte o Tasmota ao broker MQTT de sua escolha. Aqui, foi utilizado o Mosquitto, rodando como add-on no Home Assistant.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/16.png)

Assim que conectado, são criados topicos associados ao dispositivo. Na imagem abaixo, o software [MQTT Explorer](http://mqtt-explorer.com/) foi utilizado para visualização dos topicos e valores no broker MQTT.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/17.png)

## Consoles

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/18.png)

### Console

Abaixo podemos ver o console do Tasmota. Quando enviamos o comando **power off**, o relé é desativado e o estado atualizado no respectivo topico MQTT.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/19.png)

Similarmente, se publicamos **on** no topico **cmnd/tasmota_01/POWER**, o relé é acionado.

![Alt text](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT/blob/main/imagens/20.png)

  # ✅ Guia de Melhoria de Estabilidade do Tasmota

## 1. **Atualize o firmware**
- Sempre use a **versão estável mais recente** (`tasmota.bin.gz`).
- Evite o `tasmota-lite` em dispositivos com sensores, regras ou uso MQTT intenso.
- Use OTA com:
  ```
  OtaUrl http://ota.tasmota.com/tasmota/release/tasmota.bin.gz
  Upgrade 1
  ```

---

## 2. **Desative recursos que consomem memória desnecessariamente**

| Comando              | Efeito                                 |
|----------------------|------------------------------------------|
| `SetOption57 0`      | Desativa SensorRetain                   |
| `SetOption4 0`       | Desativa MQTT Retain                    |
| `WebLog 2`           | Mantém nível de log leve/moderado       |
| `SerialLog 0`        | Desativa log serial se não usado        |
| `SetOption3 0`       | Evita reinício ao perder MQTT           |
| `SetOption55 0`      | Desativa envio automático de `LWT`      |

---

## 3. **Configure corretamente o Wi-Fi**

- Use **SSID estável**, de 2.4 GHz.
- Evite redes com nomes com espaços ou acentos.
- Atribua **IP fixo** para reduzir tempo de reconexão:
  ```
  IPAddress1 10.0.0.50
  IPAddress2 10.0.0.1
  IPAddress3 255.255.255.0
  IPAddress4 8.8.8.8
  ```

> ### ⚠️ E se o firmware não suportar IP fixo?
> Alguns firmwares (como versões lite) não oferecem suporte à configuração manual de IP.
> 
> ✅ Alternativas:
> 
> - **Reserva de IP no roteador (via DHCP):**
>   Configure o roteador para atribuir sempre o mesmo IP ao MAC do Tasmota.
>
> - **Acesso via hostname/mDNS:**
>   Exemplo: `http://tasmota-bomba-aquec-piscina.local`
>
> - **Atualize para o firmware completo** (`tasmota.bin.gz`) para habilitar essa funcionalidade.

- Dica: use roteador em **modo apenas N**, canal fixo (ex: 6 ou 11).

---

## 4. **Ajustes de economia de energia (Sleep)**
- O Tasmota usa `SleepMode: Dynamic` com `Sleep: 50` por padrão (bom equilíbrio).
- Se estiver enfrentando instabilidade em sensores ou delay em comandos, pode usar:
  ```
  Sleep 0
  ```

> Isso reduz latência, mas aumenta consumo de energia.

---

## 5. **Acompanhe o desempenho (com `Status`)**
- Execute periodicamente:
  ```
  Status 0
  Status 11
  ```

- Observe:
  - `Heap` — deve estar **acima de 20 KB**
  - `LoadAvg` — abaixo de **100** é ideal
  - `RestartReason` — evite "Exception" ou "Hardware Watchdog"

---

## 6. **Evite uso excessivo de regras e timers**
- Regras mal escritas ou em loop podem consumir heap e causar reinicializações.
- Priorize automações externas (Node-RED, Home Assistant, etc.).

---

## 7. **Desligue sensores não usados**
- Tasmota carrega drivers automaticamente. Se estiver usando firmware com sensores desnecessários, compile sua própria versão ou use comandos como:
  ```
  Module 1  // Sonoff Basic, sem sensores extras
  ```

---

## 8. **Configure Telemetria corretamente**
- Para enviar status regularmente ao broker ou monitoramento:
  ```
  TelePeriod 60
  ```

> Menores que isso causam mais tráfego e uso de heap.

---

## 9. **Use fontes de alimentação confiáveis**
- Use **fontes estáveis de 3.3V ou 5V** com corrente mínima de 500 mA.
- Adicione **capacitores de 100μF e 0.1μF** próximos ao chip (ESP8266/ESP8285) para evitar resets por ruído.

---

## 10. **Monitore remotamente**
- Use painel web (como o que criamos) ou MQTT + Grafana/InfluxDB para alertas automáticos.
- Crie alertas para:
  - Heap < 20
  - LoadAvg > 100
  - RestartReason = Exception

---

# ✅ Comandos para Melhorar Estabilidade do Tasmota

Este guia traz os comandos essenciais a serem aplicados no console web do Tasmota para aumentar a estabilidade, reduzir reinicializações e evitar falhas de conexão.

---

## 📶 Wi-Fi mais confiável

```bash
SetOption56 0
```

**Descrição:** Reativa reconexão automática ao Wi-Fi.

---

## 🧠 Reduzir uso de memória (heap)

```bash
WebLog 2
SerialLog 0
MqttLog 0
```

**Descrição:**

* `WebLog 2`: mantém logs úteis sem sobrecarregar
* `SerialLog 0`: libera memória (se você não usa porta serial)
* `MqttLog 0`: reduz tráfego e uso de heap

---

## 🚫 Desativar mensagens MQTT retidas (retain)

```bash
SetOption4 0
SetOption57 0
PowerRetain 0
SensorRetain 0
```

**Descrição:** Evita retenção de mensagens antigas que podem ativar dispositivos por engano após uma reinicialização ou reconexão MQTT.

---

## ⚡ Evitar reinícios automáticos

```bash
SetOption3 0
```

**Descrição:** Impede que o dispositivo reinicie automaticamente ao perder conexão com o broker MQTT.

---

## 🧪 Telemetria regular e confiável

```bash
TelePeriod 60
```

**Descrição:** Envia status completo a cada 60 segundos, ideal para dashboards e monitoramento.

---

## 🔧 Sleep e performance

```bash
Sleep 50
```

**Descrição:** Valor padrão recomendado. Para respostas mais rápidas, use `Sleep 0` (aumenta consumo de energia).

---

## (Opcional) IP fixo no dispositivo (se suportado)

```bash
IPAddress1 10.0.0.48     # IP do Tasmota
IPAddress2 10.0.0.1      # Gateway
IPAddress3 255.255.255.0 # Máscara
IPAddress4 8.8.8.8       # DNS
```

**Alternativa:** Configure IP fixo via DHCP reservado no roteador.

---

## ✅ Conjunto mínimo recomendado

```bash
SetOption4 0
SetOption57 0
SetOption3 0
WebLog 2
SerialLog 0
TelePeriod 60
```

Aplicar esse conjunto básico melhora significativamente a estabilidade geral da rede Tasmota.

---

**📌 Observação final:**
Esses comandos podem ser aplicados diretamente via Console Web de cada Tasmota ou por automações via MQTT.

---

**Autor:** Gerado com ajuda do ChatGPT · [OpenAI](https://openai.com)






