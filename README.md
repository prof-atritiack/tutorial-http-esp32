# **Requisições HTTP GET com ESP32 (Arduino IDE)**

Este guia apresenta o passo a passo para configurar seu DOIT ESP32 DEVKIT V1 e realizar requisições HTTP GET com a biblioteca HTTPClient. O exemplo utiliza a API da OpenWeatherMap, mas pode ser adaptado para qualquer outro serviço REST.

---

## 🧰 Requisitos

- Placa DOIT ESP32 DEVKIT V1
- Cabo micro USB
- Arduino IDE 2 instalada
- Acesso à internet via Wi-Fi
- Conta gratuita na [OpenWeatherMap](https://openweathermap.org/api)

> ⚠️ O ESP32 **não se conecta a redes 5 GHz**. Use uma rede 2.4 GHz ou hotspot configurado corretamente.

---

## 🛠️ Etapa 1: Configuração da IDE


1. Vá em **File > Preferences**
2. Em **Additional Board URLs**, adicione:
   ```
   https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
   ```
3. Acesse o **Boards Manager**, busque por `esp32` e instale o pacote da Espressif Systems
4. Clique em **Select Other Board and Port**
5. Escolha a placa **DOIT ESP32 DEVKIT V1** e selecione a porta COM (geralmente COM5 nos laboratórios)

---

## 📦 Etapa 2: Bibliotecas Utilizadas

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

## 🔐 Etapa 3: Criar Conta na OpenWeatherMap

1. Acesse [openweathermap.org](https://openweathermap.org)
2. Crie uma conta gratuita
3. No painel, vá até **API Keys**
4. Gere uma chave (API Key) e copie para uso no código

---

## 💻 Etapa 4: Obter o Código de Exemplo

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

## ✅ Conclusão

Você aprendeu a conectar o ESP32 à internet e fazer requisições HTTP GET para uma API pública. Isso abre portas para integração com sistemas de clima, sensores urbanos, dashboards e muito mais.

---

## 📄 Licença

Este projeto está licenciado sob os termos da **MIT License**. Você pode usar, modificar e distribuir livremente, desde que mantenha os créditos ao autor original.

Consulte o arquivo `LICENSE` para mais detalhes.

---

## 🔗 Fontes e Referências

- [OpenWeatherMap API Docs](https://openweathermap.org/current)
- [HTTPClient Library - Espressif](https://github.com/espressif/arduino-esp32/tree/master/libraries/HTTPClient)
- [Random Nerd Tutorials - ESP32 HTTP GET](https://randomnerdtutorials.com/esp32-http-get-openweathermap-arduino/)

> 🛠️ **Este tutorial foi gerado com o apoio do ChatGPT, com base em fontes oficiais e práticas de laboratório.**

