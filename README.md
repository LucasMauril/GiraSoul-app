<div align="center">
  <h1>🌻 Gira Soul v4.0</h1>
  <p><b>Ecossistema Resiliente de Monitorização Solar e Rastreador (2 Eixos)</b></p>
  
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=Arduino&logoColor=white" />
  <img src="https://img.shields.io/badge/ESP32-000000?style=for-the-badge&logo=espressif&logoColor=white" />
  <img src="https://img.shields.io/badge/Oracle_Cloud-F80000?style=for-the-badge&logo=oracle&logoColor=white" />
  <img src="https://img.shields.io/badge/Three.js-000000?style=for-the-badge&logo=three.js&logoColor=white" />
</div>

<br>

> Mais do que um visor de telemetria, o Gira Soul v4.0 é uma plataforma educacional e tecnológica que demonstra a diferença de viabilidade econômica e de geração de energia limpa (pegada de carbono) entre painéis solares fixos e painéis com rastreamento ativo.

## ✨ Principais Funcionalidades

* 🔌 **Resiliência Offline-First:** O sistema em feiras científicas funciona sem nenhuma ligação externa. Bibliotecas pesadas (Chart.js, Three.js) são processadas localmente no disco, tornando o stand imune a falhas de Wi-Fi.
* 🧊 **Gêmeo Digital 3D (Three.js):** Uma representação tridimensional do painel físico a 60fps. O ângulo de inclinação do hardware físico afeta diretamente a renderização no ecrã.
* 🔄 **CloudFetcher (Modo Espelho):** Sincronização bidirecional que capta as medições do ESP32 na Oracle Cloud através de *Server-Sent Events* e injeta no painel local via WebSocket.
* 🎮 **Simulador Matemático Integrado:** Para testes em dias de chuva, um simulador Python com curvas senoidais e funções de azimute solar substitui o hardware por software, injetando dados realistas.

## 🛠️ Arquitetura de Hardware Descentralizada

Para evitar falhas únicas e garantir a estabilidade do sistema, o processamento foi dividido em três microcontroladores independentes:

1. **Arduino Mega 2560 (O Cérebro Local):** Lê os 4 sensores LDR e os sensores de tensão/corrente via I2C, calculando o vetor de luz em elevação/azimute para mover os servomotores do painel principal de forma fluida (usando *deadbands*).
2. **ESP32 (Ponte Wi-Fi e Segurança):** Gateway que recebe os dados via porta Serial e comunica de forma encriptada (HTTPS) com o servidor REST. Possui *watchdog* de hardware para reiniciar apenas o rádio em caso de travamento.
3. **Arduino Uno (Mini-Tracker Autônomo):** Uma maquete de demonstração pedagógica que corre num circuito 100% isolado com 2 micro-servos.

## 🔒 Segurança de Nível Acadêmico

* **Nuvem Blindada (MAC Lock):** O nosso servidor central Oracle Flask só aceita pedidos HTTP que contenham o MAC Address exato do nosso ESP32, impedindo ataques externos.
* **Criptografia Desktop (DPAPI):** O aplicativo desktop em Windows encripta localmente chaves de API e senhas sensíveis de forma nativa, protegendo contra roubo de credenciais em feiras públicas.

## 🚀 Como testar o projeto (App Executável)

Este repositório serve como distribuição oficial do painel de telemetria do projeto. O frontend não necessita de frameworks pesados (React/Angular). O motor Python utiliza a *engine* WebView2 (Edge Chromium) para servir o sistema como um programa nativo do Windows.

Para utilizar:
1. Faça o download do arquivo **Gira Soul.exe** disponível nos arquivos deste repositório.
2. Execute-o no Windows.
3. Se você não possuir a maquete física, clique nas configurações e ative o **Modo Simulação** para ver toda a interface, gráficos 3D e cálculos de economia em ação.

*(Nota: O código-fonte completo de hardware, nuvem e backend deste projeto encontra-se em repositório privado para segurança do projeto institucional).*

---
<div align="center">
  <sub>Desenvolvido com 💚 por estudantes do SESI - Edição 2026 </sub>
</div>
