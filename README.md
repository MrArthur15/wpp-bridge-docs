# WPP Business Bridge (Middleware de Integração Enterprise)

![JavaScript](https://img.shields.io/badge/JavaScript-111B21?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![Node.js](https://img.shields.io/badge/Node.js-111B21?style=for-the-badge&logo=nodedotjs&logoColor=339933)
![C#](https://img.shields.io/badge/C%23-111B21?style=for-the-badge&logo=c-sharp&logoColor=239120)
![MySQL](https://img.shields.io/badge/MySQL-111B21?style=for-the-badge&logo=mysql&logoColor=4479A1)
![Chrome Extensions](https://img.shields.io/badge/Chrome_Extensions-111B21?style=for-the-badge&logo=google-chrome&logoColor=4285F4)

**WPP Business Bridge** é uma arquitetura de middleware distribuída, desenvolvida para integrar fluxos de comunicação em tempo real (WhatsApp) com ecossistemas de back-end corporativos (.NET Core / MySQL). O sistema atua como um barramento de dados seguro, resiliente e escalável entre a interface web e o servidor de negócio.

---

## 🏗️ Arquitetura do Sistema (3-Tier)

O sistema foi projetado seguindo princípios de separação de responsabilidades (SoC), garantindo escalabilidade e desacoplamento:

1. **Frontend (Browser Extension - `wpp-bridge-ui`):** Camada de observabilidade (DOM Observer) que atua na interface do usuário para captura de eventos e injeção de dados.
2. **Middleware (Node.js Engine - `wpp-bridge-core`):** O orquestrador central. Gerencia WebSockets, persistência de sessão local, fila de processos (Mutex Lock) e comunicação assíncrona.
3. **Backend (.NET Core):** A inteligência de negócio. Camada de persistência (MySQL) que gerencia regras de envio, fila de mensagens (Outbound) e validação de segurança via `X-API-KEY`.

---

## 🚀 Funcionalidades Principais

* **Inbound Pipeline:** Captura eventos em tempo real com triagem temporal (Backlog vs. Tempo Real), garantindo que mensagens sejam salvas no banco de dados com a origem correta.
* **Outbound Radar:** Engine de *polling* que consulta o banco de dados periodicamente, processa disparos de mensagens e realiza a confirmação atômica de entrega, evitando loops e duplicidade.
* **Resiliência (Self-Healing):** Rotinas de *Heartbeat* que detectam quedas de conexão e restabelecem o fluxo automaticamente, garantindo alta disponibilidade.
* **Segurança de Borda:** Comunicação autenticada stateless via cabeçalhos HTTP, garantindo que apenas instâncias autorizadas consigam injetar dados no motor.

---

## ⚠️ Disclaimer (Aviso Legal)
Este repositório é uma **documentação de arquitetura de referência** para fins educacionais e de pesquisa em engenharia de software corporativo. O código-fonte real dos módulos é mantido em repositórios privados para segurança de propriedade intelectual. A implementação de qualquer automação deve respeitar rigorosamente os Termos de Serviço da plataforma utilizada.

---
<br><br>

<div align="center">
  <img src="https://img.shields.io/badge/SYSTEM_LOG-CONTEXT_SWITCH-111B21?style=for-the-badge&logo=google-translate&logoColor=00A884">
  <p><i><sub>Loading English documentation...</sub></i></p>
</div>

<br><br>

# WPP Business Bridge (Enterprise Integration Middleware)

**WPP Business Bridge** is a distributed middleware architecture developed to integrate real-time communication flows (WhatsApp) with corporate back-end ecosystems (.NET Core / MySQL). The system acts as a secure, resilient, and scalable data bus between the web interface and the business server.

---

## 🏗️ System Architecture (3-Tier)

The system was designed following separation of concerns (SoC) principles, ensuring scalability and decoupling:

1. **Frontend (Browser Extension - `wpp-bridge-ui`):** Observability layer (DOM Observer) acting on the user interface for event capture and data injection.
2. **Middleware (Node.js Engine - `wpp-bridge-core`):** The central orchestrator. Manages WebSockets, local session persistence, process queuing (Mutex Lock), and asynchronous communication.
3. **Backend (.NET Core):** The business intelligence. Persistence layer (MySQL) managing sending rules, message queuing (Outbound), and security validation via `X-API-KEY`.

---

## 🚀 Key Features

* **Inbound Pipeline:** Captures real-time events with temporal sorting (Backlog vs. Real-Time), ensuring messages are saved to the database with the correct origin.
* **Outbound Radar:** Polling engine that periodically queries the database, processes message dispatches, and performs atomic delivery confirmation, preventing loops and duplication.
* **Resilience (Self-Healing):** Heartbeat routines that detect connection drops and automatically restore the data flow, ensuring high availability.
* **Edge Security:** Stateless authenticated communication via HTTP headers, ensuring that only authorized instances can inject data into the engine.

---

## ⚠️ Disclaimer
This repository is a **reference architecture documentation** for educational and research purposes in corporate software engineering. Actual source code for the modules is kept in private repositories for intellectual property security. Usage of this system must strictly adhere to the platform's Terms of Service.
