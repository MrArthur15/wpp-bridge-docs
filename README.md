# 🌉 WPP Business Bridge (Enterprise Integration Middleware)

**WPP Business Bridge** é uma arquitetura de middleware distribuída, desenvolvida para integrar fluxos de comunicação em tempo real (WhatsApp) com ecossistemas de back-end corporativos (.NET Core / MySQL). O sistema atua como um barramento de dados seguro, resiliente e escalável entre a interface web e o servidor de negócio.

---

<div align="center">
  <p>
    <a href="#-arquitetura-do-sistema">🇧🇷 Ler em Português</a> •
    <a href="#-system-architecture">🇺🇸 Read in English</a>
  </p>
</div>

---

# 🇧🇷 Arquitetura do Sistema

## 🏗️ Estrutura (3-Tier)
O ecossistema foi projetado seguindo princípios de separação de responsabilidades (SoC), garantindo que cada componente foque em sua função específica:

1. **`wpp-bridge-ui` (Frontend Extension):** Camada de observabilidade (DOM Observer) que atua na interface do usuário para captura de eventos e injeção de dados.
2. **`wpp-bridge-core` (Middleware Node.js):** O orquestrador central. Gerencia WebSockets, persistência de sessão local, fila de processos (Mutex Lock) e comunicação assíncrona.
3. **Backend (.NET Core):** A inteligência de negócio. Camada de persistência (MySQL) que gerencia regras de envio e validação de segurança via `X-API-KEY`.

## 🚀 Funcionalidades Principais
* **Processamento Assíncrono:** Fila de mensagens em RAM com controle de concorrência.
* **Resiliência (Self-Healing):** Rotinas de *Heartbeat* que detectam quedas e restabelecem o fluxo.
* **Auditoria Transacional:** Rastreabilidade completa desde a injeção até a confirmação de entrega.
* **Segurança de Borda:** Autenticação stateless validada via cabeçalhos HTTP.

---

# 🇺🇸 System Architecture

## 🏗️ 3-Tier Structure
The ecosystem was designed following separation of concerns (SoC) principles, ensuring each component focuses on its specific function:

1. **`wpp-bridge-ui` (Frontend Extension):** Observability layer (DOM Observer) acting on the user interface for event capture and data injection.
2. **`wpp-bridge-core` (Middleware Node.js):** The central orchestrator. Manages WebSockets, local session persistence, process queuing (Mutex Lock), and asynchronous communication.
3. **Backend (.NET Core):** The business intelligence. Persistence layer (MySQL) managing sending rules and security validation via `X-API-KEY`.

## 🚀 Key Features
* **Asynchronous Processing:** RAM-based message queue with concurrency control.
* **Resilience (Self-Healing):** Heartbeat routines that detect drops and automatically restore the data flow.
* **Transactional Auditing:** Full traceability from DOM injection to delivery confirmation.
* **Edge Security:** Stateless authentication validated via HTTP headers.

---

## 🛠️ Tecnologias Principais / Tech Stack

![JavaScript](https://img.shields.io/badge/JavaScript-111B21?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![Node.js](https://img.shields.io/badge/Node.js-111B21?style=for-the-badge&logo=nodedotjs&logoColor=339933)
![C#](https://img.shields.io/badge/C%23-111B21?style=for-the-badge&logo=c-sharp&logoColor=239120)
![MySQL](https://img.shields.io/badge/MySQL-111B21?style=for-the-badge&logo=mysql&logoColor=4479A1)
![Chrome](https://img.shields.io/badge/Chrome_Extensions-111B21?style=for-the-badge&logo=google-chrome&logoColor=4285F4)

---

## ⚠️ Disclaimer (Aviso Legal)
Este repositório é uma **documentação de arquitetura de referência** para fins educacionais e de pesquisa em engenharia de software corporativo. O código-fonte real dos módulos (`core` e `ui`) é mantido em repositórios privados para segurança de propriedade intelectual. O uso deste sistema deve respeitar os Termos de Serviço da plataforma. 

*This repository provides **reference architecture documentation** for educational and research purposes. Actual source code for the modules (`core` and `ui`) is kept in private repositories for intellectual property security. Usage of this system must strictly adhere to the platform's Terms of Service.*
