# **Requisições HTTP GET com ESP32 (Arduino IDE)**

⚠️ Importante: Este exemplo utiliza requisição HTTP (não HTTPS). APIs que exigem HTTPS podem não funcionar corretamente sem configuração adicional no ESP32. Verifique se a API utilizada permite requisições via http://.

Este guia apresenta o passo a passo para configurar seu DOIT ESP32 DEVKIT V1 e realizar requisições HTTP GET com a biblioteca HTTPClient. O exemplo utiliza a API da OpenWeatherMap, mas pode ser adaptado para qualquer outro serviço REST.

---

## Requisitos

- Placa DOIT ESP32 DEVKIT V1
- Cabo micro USB
- Arduino IDE 2 instalada
- Acesso à internet via Wi-Fi
- Conta gratuita na [OpenWeatherMap](https://openweathermap.org/api)

> ⚠️ O ESP32 **não se conecta a redes 5 GHz**. Use uma rede 2.4 GHz ou hotspot configurado corretamente.

---

## Etapa 1: Configuração da IDE Arduino

> **Observação importante:** Nos computadores do laboratório, as placas ESP32 já estão instaladas na IDE.
> A seção a seguir é útil apenas para instalação em computadores pessoais.
> Se está em um computador já configurado, pule para a seção 1.2.

### 1.1 Instalação da Placa ESP32 (apenas para uso em computadores próprios)

1. Abra a Arduino IDE
2. Vá em **File > Preferences**
3. No campo **"Additional Board URLs"**, adicione:
   ```
   https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
   ```
4. Clique em **OK**
5. Vá até a aba **Boards Manager** (ícone de placa no menu lateral)
6. Busque por **esp32** e instale o pacote da Espressif Systems

> ⚠️ Módulos DOIT ESP32 DEVKIT V1 podem exigir drivers para comunicação USB. Caso sua placa não apareça nas portas disponíveis, instale os drivers CP210x:  
> [Baixar Drivers USB CP210x (Windows)](https://randomnerdtutorials.com/install-esp32-esp8266-usb-drivers-cp210x-windows/#more-148082)

### 1.2 Configurações Básicas da Arduino IDE

- Ajuste as opções da IDE, no menu File ---> Preferences:
- Escolha o tamanho da fonte de sua preferência.
- Escolha o tema de sua preferência.
- Habilite a opção "Editor Quicks Suggestions".

### 1.3  Seleção da Placa e Porta

- Na Arduino IDE, clique em **"Select Other Board and Port"** na parte superior da tela
- Digite na busca "DEV ou DOIT" e selecione a placa **DOIT ESP32 DEVKIT V1**
- Conecte a placa ao computador via cabo USB (não utilize a extensão, conecte direto na USB)
- Selecione a porta COM correta (geralmente **COM5** nos laboratórios)
- Ajuste a velocidade de comunicação do Serial Monitor (ícone do Serial Monitor, no canto superior direito da tela):
**Velocidade do Monitor Serial**: 115200 bauds
  
---

## Etapa 2: Bibliotecas Utilizadas

O exemplo utiliza as seguintes bibliotecas:

- `WiFi` (já incluída com ESP32)
- `HTTPClient` (também incluída com ESP32)
- `Arduino_JSON` (precisa ser instalada manualmente)

### Como instalar a Arduino_JSON:

1. Abra o **Library Manager** na Arduino IDE
2. Procure por **Arduino_JSON** (atenção ao nome exato)
3. Instale a versão mais recente

Essa biblioteca é utilizada para interpretar os dados JSON retornados pela API da OpenWeatherMap de forma prática e leve.

---

## Etapa 3: Criar Conta na OpenWeatherMap

1. Acesse [openweathermap.org](https://openweathermap.org)
2. Crie uma conta gratuita
3. No painel, vá até **API Keys**
4. Gere uma chave (API Key) e copie para uso no código

---

## Etapa 4: Obter o Código de Exemplo

O código completo está neste repositório.

- Clone ou baixe o projeto disponível nesta página
- Abra o arquivo `ESP32_HTTP_GET_SIMPLES` dentro da pasta `codigo`
- Atualize as seguintes variáveis:
  - `SECRET_SSID` e `SECRET_PW` com sua rede Wi-Fi
  - `apiKey` com sua chave da OpenWeatherMap  

Depois:

- Clique em **Upload** para carregar o código na placa
- Abra o **Serial Monitor** (115200 bauds)
- Observe o retorno da API com as informações do clima

---

## Conclusão

Você aprendeu a conectar o ESP32 à internet e fazer requisições HTTP GET para uma API pública. Isso abre portas para integração com sistemas de clima, sensores urbanos, dashboards e muito mais.

---

## Licença

Este projeto está licenciado sob os termos da **MIT License**. Você pode usar, modificar e distribuir livremente, desde que mantenha os créditos ao autor original.

Consulte o arquivo `LICENSE` para mais detalhes.

---

## 🔗 Fontes e Referências

- [OpenWeatherMap API Docs](https://openweathermap.org/current)
- [HTTPClient Library - Espressif](https://github.com/espressif/arduino-esp32/tree/master/libraries/HTTPClient)
- [Random Nerd Tutorials - ESP32 HTTP GET](https://randomnerdtutorials.com/esp32-http-get-openweathermap-arduino/)

> 🛠**Este tutorial foi gerado com o apoio do ChatGPT, com base em fontes oficiais e práticas de laboratório.**

