# WPA Field Audit - Proof of Concept (PoC)

![Badge Status](https://img.shields.io/badge/Status-Em_Desenvolvimento-yellow)
![Badge Flutter](https://img.shields.io/badge/Tecnologia-Flutter-blue)
![Badge Context](https://img.shields.io/badge/Contexto-Field_Service-green)

## 📌 Sobre o Projeto

Este projeto é um protótipo funcional desenvolvido como parte do curso de **Sistemas de Informação**. 

O objetivo é apresentar uma proposta de modernização para o processo de execução de notas comerciais em campo (WPA), focado na resolução de problemas de **Qualidade de Dados** e **Auditoria de Imagens**.

Atualmente, a execução de serviços (como troca de medidores) sofre com a falta de padronização nas fotos coletadas, gerando retrabalho e falhas na auditoria. Este aplicativo propõe uma mudança de paradigma: de um "formulário aberto" para um **Fluxo Guiado (Wizard)**.

## 🚀 Solução Proposta

| Cenário Atual (As Is) | Cenário Proposto (To Be) |
| :--- | :--- |
| Fotos tiradas de forma aleatória | **Checklist Guiado:** O app diz o que fotografar |
| Falta de padrão (ângulo/foco) | **Câmera com Overlay:** Máscara na tela guiando o enquadramento |
| Envio de notas incompletas | **Bloqueio Lógico:** Só finaliza se todas as evidências forem coletadas |
| Auditoria manual e demorada | **Pré-auditoria:** Validação na ponta (Edge Computing) |

## 🛠 Tecnologias Utilizadas

* **Linguagem:** Dart
* **Framework:** Flutter (Mobile)
* **Gerenciamento de Estado:** (Defina aqui: ex: Provider, MobX ou ValueNotifier)
* **Backend (Simulado):** Firebase (Firestore + Storage)
* **Persistência Local:** SQLite (Simulação de modo Offline-First)

## 📱 Funcionalidades Chave

- [x] **Login do Eletricista:** Autenticação simples.
- [x] **Lista de Serviços:** Visualização das notas atribuídas ao técnico.
- [ ] **Fluxo Guiado (Wizard):** Interface passo-a-passo para execução.
- [ ] **Smart Camera:** Overlay (máscara) sobre a câmera para padronizar fotos de medidores.
- [ ] **Validação Offline:** Otimização para áreas sem sinal.

## 📂 Arquitetura do Projeto

O projeto segue uma estrutura modular para facilitar a escalabilidade e manutenção:

```bash
lib/
├── core/           # Configurações globais, temas e utilitários
├── data/           # Repositories e serviços (Firebase/SQLite)
├── models/         # Modelos de dados (Nota, EtapaAuditoria)
├── modules/        # Telas separadas por funcionalidade
│   ├── auth/       # Login
│   ├── home/       # Listagem de serviços
│   └── execucao/   # O fluxo guiado (Core do TCC)
└── widgets/        # Componentes reutilizáveis (Botões, Cards, CameraOverlay)
