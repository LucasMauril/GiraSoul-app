# 🌻 Gira Soul - App Desktop (v4.0)

Este repositório contém a versão **executável oficial** do aplicativo de telemetria do projeto **Gira Soul**. 

## 🔋 O que é o Gira Soul?

O Gira Soul é um ecossistema de hardware e software criado para fins educacionais e feiras de ciências. Seu principal objetivo é **demonstrar na prática a diferença de eficiência e viabilidade econômica entre painéis solares fixos e painéis com rastreamento ativo (Solar Trackers)**.

O sistema físico (maquete) utiliza LDRs e servomotores controlados por Arduino para sempre "mirar" no sol, enquanto sensores de tensão e corrente medem o ganho de energia gerado.

## 💻 Sobre este Aplicativo

Este executável é a interface gráfica (Dashboard) do sistema, desenvolvida em **Python (PyWebView)** com **HTML/JS**. 

Suas principais funções são:
- 📊 **Monitoramento ao Vivo:** Lê os dados seriais via USB do Arduino (ou remotamente da nuvem) e gera gráficos de Watts, Tensão, Corrente e Temperatura.
- 💰 **Cálculo de Eficiência:** Compara a energia gerada pelo Tracker versus a simulação de um painel fixo, traduzindo o ganho em Reais (R$) e carbono (CO₂) evitado.
- 📡 **Integração em Nuvem:** Capacidade de buscar dados remotamente de servidores Oracle Cloud, espelhando os sensores de uma feira para o computador na sala de aula.
- 🖨️ **Geração de Relatórios:** Exportação local de dados em CSV, Excel e impressão de relatórios em PDF para os avaliadores do projeto.

---

### 🚀 Como utilizar

1. Faça o download do arquivo **Gira Soul.exe** deste repositório.
2. Execute-o em seu computador com Windows.
3. Se possuir o hardware da maquete, basta conectar o cabo USB (O app fará o auto-scan da porta COM).
4. Caso não possua o hardware, ative o **"Modo Simulação"** nas configurações do aplicativo para ver a interface em funcionamento com dados artificiais.

*(Nota: O código-fonte completo de hardware, nuvem e backend deste projeto se encontra em repositório privado para segurança dos tokens da instituição).*
