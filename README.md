# O que é Tasmota?

Tasmota é um firmware de código aberto projetado para dispositivos baseados no microcontrolador **ESP8266** e, mais recentemente, **ESP32**. Ele é amplamente utilizado em projetos de automação residencial e Internet das Coisas (IoT). O principal objetivo do Tasmota é substituir o firmware proprietário em dispositivos inteligentes, permitindo maior controle e personalização por parte do usuário.

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

## Instalação e uso com o Home Assistant

Acesse este repositório que contem as descrições de instalação do Tasmota e o uso com a plataforma Home Assistant

[Instalação e uso com Home Assistant](https://github.com/Epaminondaslage/HomeAssistant-Tasmota-MQTT)



# Estrutura de Tópicos MQTT no Tasmota

A estrutura de tópicos de um dispositivo Tasmota no MQTT segue uma hierarquia bem definida, permitindo comunicação bidirecional entre o dispositivo e o servidor MQTT. Essa estrutura é flexível e configurável, mas geralmente utiliza os prefixos `cmnd`, `stat` e `tele` combinados com o tópico base do dispositivo.

## Configuração de Tópicos MQTT no Tasmota

1. Acesse o dispositivo Tasmota via navegador.
2. Vá para **Configuration > Configure MQTT**.
3. Configure os campos:
   - **Full Topic**:  
     Geralmente, o padrão é `%prefix%/%topic%/`, o que gera a estrutura descrita.
   - **Topic**:  
     Nome único para identificar o dispositivo (ex.: `tasmota_lampada01`).

Com essa estrutura, o dispositivo Tasmota pode ser facilmente integrado a sistemas como **Home Assistant**, **Node-RED**, ou qualquer servidor MQTT.


## 1. Prefixos Padrão

| **Prefixo** | **Função**                    | **Exemplo de Tópico**           | **Descrição**                                                            |
|-------------|-------------------------------|----------------------------------|--------------------------------------------------------------------------|
| `cmnd`      | Comandos enviados ao dispositivo | `cmnd/tasmota_lampada01/POWER`  | Enviar comandos para ligar/desligar, alterar brilho, etc.                |
| `stat`      | Estado do dispositivo         | `stat/tasmota_lampada01/POWER`  | Retorna o estado atual do relé ou resposta a um comando.                 |
| `tele`      | Dados periódicos/telemetria   | `tele/tasmota_lampada01/SENSOR` | Envia dados de sensores ou status periódico (temperatura, umidade, etc.) |

---

## 2. Estrutura Geral

A estrutura básica de um tópico MQTT no Tasmota é:

```
<prefix>/<topic>/<subtopic>
```

- **`<prefix>`**: Prefixo como `cmnd`, `stat`, ou `tele`.
- **`<topic>`**: Nome único do dispositivo configurado no campo **Topic** do Tasmota.
- **`<subtopic>`**: Um identificador que indica o tipo de dado ou comando (ex.: `POWER`, `SENSOR`, `LWT`).

---

## 3. Exemplos de Tópicos

### **Comandos (`cmnd`)**
Usados para controlar o dispositivo:

- **Ligar/Desligar relé**:
  ```
  cmnd/tasmota_lampada01/POWER
  ```
  **Payload**:
  - `"ON"` para ligar.
  - `"OFF"` para desligar.

- **Alterar brilho (se aplicável)**:
  ```
  cmnd/tasmota_lampada01/DIMMER
  ```
  **Payload**:
  - Valor de 0 a 100 (percentual).

---

### **Estado (`stat`)**
Usados para receber o estado atual do dispositivo:

- **Estado do relé**:
  ```
  stat/tasmota_lampada01/POWER
  ```
  **Payload**:
  - `"ON"` ou `"OFF"`.

- **Resultado de um comando**:
  ```
  stat/tasmota_lampada01/RESULT
  ```
  **Payload**:
  ```json
  {
    "POWER": "ON"
  }
  ```

---

### **Telemetria (`tele`)**
Usados para informações periódicas:

- **Status do dispositivo**:
  ```
  tele/tasmota_lampada01/STATE
  ```
  **Payload** (em JSON):
  ```json
  {
    "Time": "2024-12-20T14:00:00",
    "Uptime": "1T00:00:00",
    "Vcc": 3.171,
    "POWER": "ON"
  }
  ```

- **Dados de sensores**:
  ```
  tele/tasmota_lampada01/SENSOR
  ```
  **Payload** (em JSON):
  ```json
  {
    "Time": "2024-12-20T14:00:00",
    "DHT11": {
      "Temperature": 25.0,
      "Humidity": 60
    }
  }
  ```

- **Última vontade e testamento (LWT)**:  
  Publica o status de conectividade do dispositivo:
  ```
  tele/tasmota_lampada01/LWT
  ```
  **Payload**:
  - `"Online"`: Dispositivo conectado.
  - `"Offline"`: Dispositivo desconectado.

---


