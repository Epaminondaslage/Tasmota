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

# Configuração de MQTT no Tasmota para o dispositivo "Alarme"

## Configuração Atualizada

- **Host:** Endereço IP ou domínio do broker MQTT (deve ser preenchido, por exemplo, `10.0.0.32`).
- **Port:** 1883 (porta padrão para conexões MQTT não seguras).
- **MQTT TLS:** Desativado (não há criptografia configurada).
- **Client ID:** `Alarme` (ID único do dispositivo no servidor MQTT).
- **User:** `DVES_USER` (nome de usuário para autenticação).
- **Password:** (não fornecido, deve ser configurado).
- **Topic Base:** `%topic%` (substituído por `Alarme`).
- **Full Topic:** `%prefix%/%topic%/` (estrutura dinâmica para tópicos).

---

## Como os tópicos são gerados

### 1. Tópico para comandos (`cmnd`):
Este tópico é usado para enviar comandos ao dispositivo.

- **Exemplo de Tópico:**
  ```
  cmnd/Alarme/POWER
  ```
- **Descrição:** Envia um comando para ligar/desligar o relé do dispositivo.

- **Payloads:**
  - `"ON"`: Liga o relé.
  - `"OFF"`: Desliga o relé.

---

### 2. Tópico para estado (`stat`):
Este tópico é usado para receber o estado atual do dispositivo.

- **Exemplo de Tópico:**
  ```
  stat/Alarme/POWER
  ```
- **Descrição:** Retorna o estado atual do relé do dispositivo.

- **Payloads:**
  - `"ON"`: Relé está ligado.
  - `"OFF"`: Relé está desligado.

---

### 3. Tópico para telemetria (`tele`):
Este tópico é usado para dados periódicos, como sensores ou status do dispositivo.

- **Exemplo de Tópico:**
  ```
  tele/Alarme/STATE
  ```
- **Descrição:** Publica o estado completo do dispositivo, como tempo de atividade, status do relé e tensão.

- **Payload (em JSON):**
  ```json
  {
    "Time": "2024-12-20T14:00:00",
    "Uptime": "1T00:00:00",
    "Vcc": 3.171,
    "POWER": "ON"
  }
  ```

---

### 4. Última vontade e testamento (LWT):
Este tópico publica o status de conectividade do dispositivo.

- **Exemplo de Tópico:**
  ```
  tele/Alarme/LWT
  ```
- **Descrição:** Indica se o dispositivo está conectado ou não.

- **Payloads:**
  - `"Online"`: Dispositivo conectado.
  - `"Offline"`: Dispositivo desconectado.

---

## Como usar em uma integração (Node-RED ou Home Assistant)

### Node-RED:
- Use um nó **MQTT In** para assinar tópicos como `stat/Alarme/#` para receber todos os estados.
- Use um nó **MQTT Out** para publicar em `cmnd/Alarme/POWER` e controlar o dispositivo.

### Home Assistant:
Configure o dispositivo em `configuration.yaml`:

```yaml
mqtt:
  switch:
    - name: "Alarme"
      command_topic: "cmnd/Alarme/POWER"
      state_topic: "stat/Alarme/POWER"
      payload_on: "ON"
      payload_off: "OFF"
      state_on: "ON"
      state_off: "OFF"
```

---

# O que é LWT?

LWT, ou **Last Will and Testament** (Última Vontade e Testamento), é um recurso do protocolo MQTT projetado para indicar o status de conectividade de um cliente MQTT (neste caso, um dispositivo, como um Tasmota) ao broker MQTT. Ele é configurado quando o cliente se conecta ao broker e funciona como uma mensagem que será publicada automaticamente se o cliente perder a conexão inesperadamente.

---

## **Como funciona o LWT?**
1. **Configuração na conexão:**  
   - Quando um cliente MQTT se conecta ao broker, ele pode registrar um tópico LWT, especificando a mensagem que deve ser publicada caso ele se desconecte de forma inesperada.
   - Esse tópico e a mensagem são armazenados pelo broker MQTT.

2. **Publicação automática pelo broker:**  
   - Se o cliente perder a conexão sem enviar um comando de desconexão ("disconnect"), o broker publica a mensagem LWT no tópico configurado.

3. **Detecção de conectividade:**  
   - Outros clientes que estão assinados ao tópico LWT podem usar essa mensagem para detectar que o cliente perdeu a conexão.

---

## **Exemplo de uso no Tasmota**
No firmware Tasmota, o LWT é usado para indicar se o dispositivo está conectado ou desconectado do broker MQTT. Por padrão, ele utiliza o tópico de telemetria com o subtópico **LWT**.

### **Configuração padrão:**
- **Tópico:**  
  ```
  tele/<topic>/LWT
  ```
  Exemplo para um dispositivo chamado "Alarme":
  ```
  tele/Alarme/LWT
  ```

- **Mensagens (payloads):**
  - `"Online"`: Indica que o dispositivo está conectado ao broker MQTT.
  - `"Offline"`: Indica que o dispositivo perdeu a conexão inesperadamente.

---

## **Exemplo prático**
1. **Quando o dispositivo conecta:**
   - O Tasmota publica automaticamente a mensagem `"Online"` no tópico `tele/Alarme/LWT`.

2. **Quando o dispositivo desconecta de forma inesperada:**
   - O broker publica a mensagem `"Offline"` no tópico `tele/Alarme/LWT`.

3. **Como usar essa informação:**
   - **Home Assistant:** Você pode monitorar o status do dispositivo para criar automações, como alertas de desconexão.
   - **Node-RED:** Pode ser usado para detectar falhas e acionar ações corretivas.

---

## **Benefícios do LWT**
- **Monitoramento de conectividade:** Ajuda a garantir que o estado de um dispositivo MQTT seja conhecido, mesmo que ele perca a conexão inesperadamente.
- **Automação e confiabilidade:** Permite criar respostas automáticas a desconexões, como reinicialização de dispositivos ou envio de alertas.
- **Diagnóstico de falhas:** Facilita a identificação de problemas na rede ou nos dispositivos.

O LWT é um recurso essencial para sistemas IoT que dependem da conectividade contínua para funcionar de maneira confiável.


