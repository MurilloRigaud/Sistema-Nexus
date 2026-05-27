<div align="center">

<br>

<img src="https://img.shields.io/badge/Nexus-Monitor%20de%20Aprendizagem-2e8b57?style=for-the-badge&logoColor=white" alt="Nexus" />

# Nexus — Monitor de Evasão Inteligente

**Sistema de recomendação educacional personalizada com detecção de risco e solução para Cold Start**

<br>

[![Status](https://img.shields.io/badge/Status-Protótipo%20Funcional-5ecf8a?style=flat-square)](.)
[![Tipo](https://img.shields.io/badge/Tipo-Trabalho%20Acadêmico-c9a227?style=flat-square)](.)
[![Tecnologia](https://img.shields.io/badge/Stack-HTML%20%7C%20CSS%20%7C%20JavaScript-42a5f5?style=flat-square)](.)
[![IA](https://img.shields.io/badge/IA-Claude%20Sonnet%204-2e8b57?style=flat-square)](.)

<br>

</div>

---

## 📌 Sobre o Projeto

O **Nexus** é um sistema externo de recomendação educacional inteligente, desenvolvido como proposta acadêmica para o problema de **evasão em cursos EAD**.

Baseado no artigo de **Andrade et al. (2025)** e no problema clássico de **Cold Start** em sistemas de recomendação, o Nexus propõe uma solução que vai além da simples detecção de risco — ele **age ativamente**, entregando ao aluno materiais personalizados para recuperar seu desempenho antes que o abandono aconteça.

O sistema é projetado como um **serviço SaaS** licenciado por instituições de ensino e integrado diretamente ao portal do aluno.

---

## 🎯 Problemática

> *"Milhares de alunos abandonam cursos EAD por baixo desempenho e falta de acompanhamento personalizado. Os sistemas atuais conseguem prever evasão, mas não oferecem suporte inteligente imediato."*

| Problema | Impacto |
|---|---|
| Taxa de evasão em EAD no Brasil | ~40% dos alunos abandonam o curso |
| Falta de suporte personalizado | 72% dos alunos em risco não recebem recomendação específica |
| Cold Start | Alunos novos sem histórico ficam sem recomendações úteis |

---

## 💡 Solução Proposta

O Nexus combina dois módulos principais:

**1. Detecção de Risco de Evasão**
Analisa notas, frequência e comportamento acadêmico do aluno para calcular um percentual de risco de evasão em tempo real.

**2. Motor de Recomendação Ativa**
Com base no perfil do aluno e nos tópicos de dificuldade declarados, gera um plano personalizado com vídeos, PDFs, exercícios, revisões e mapas mentais.

**Solução para Cold Start:** alunos sem histórico declaram manualmente os tópicos de dificuldade — o sistema usa esse dado imediato para recomendar sem precisar de histórico prévio.

---

## 🏗️ Arquitetura do Sistema

```
Portal da Faculdade (UniVerde)
        │
        │  Aluno clica em "Acessar o Nexus"
        ▼
┌─────────────────────────────────────┐
│           NEXUS                     │
│                                     │
│  [Coleta de Dados]                  │
│   Notas · Frequência · Histórico    │
│          │                          │
│          ▼                          │
│  [Detecção de Risco] ──► [Identificação de Lacunas] │
│   Modelo preditivo       Tópicos com dificuldade    │
│          │                          │
│          ▼                          │
│  [Motor de Recomendação]            │
│   Filtragem por perfil + Cold Start │
│          │                          │
│          ▼                          │
│  Vídeos · PDFs · Exercícios · Plano semanal         │
└─────────────────────────────────────┘
```

---

## 🔄 Processo CRISP-DM

O projeto segue as 6 fases do processo **CRISP-DM** de Mineração de Dados:

| Fase | Aplicação no Nexus |
|---|---|
| **1. Entendimento do Negócio** | Problema de evasão em EAD; objetivo de reduzir abandono com recomendação ativa |
| **2. Entendimento dos Dados** | Notas, frequência, histórico acadêmico e tópicos declarados pelo aluno |
| **3. Preparação dos Dados** | Normalização de notas, cálculo de frequência, conversão de tópicos em variáveis de perfil |
| **4. Modelagem** | Modelo preditivo de risco (Random Forest / Regressão Logística) + motor de recomendação híbrido |
| **5. Avaliação** | Acurácia, precisão e recall na detecção de risco; relevância das recomendações |
| **6. Implantação** | Sistema SaaS integrado ao portal — aluno acessa, modelo roda, recomendações são entregues em tempo real |

---

## 🗂️ Estrutura do Repositório

```
sistema-nexus/
│
├── telas/
│   ├── portal-univerde.html     # Portal da faculdade fictícia (UniVerde)
│   └── nexus-sistema.html       # Sistema Nexus com recomendações via IA
│
├── pitch-nexus.html             # Apresentação interativa (7 slides)
│
└── README.md                    # Este arquivo
```

---

## 🖥️ Telas do Sistema

### Portal UniVerde
Simula o portal de uma faculdade fictícia onde o aluno visualiza suas notas, alertas de desempenho e acessa o Nexus com um clique.

**Funcionalidades demonstradas:**
- Dashboard com notas e frequência por disciplina
- Indicadores de risco (alto / médio / baixo)
- Banner de acesso ao sistema Nexus
- Avisos e notificações acadêmicas

### Sistema Nexus
Sistema de recomendação com fluxo em 3 etapas, integrado à API do Claude para geração de recomendações reais e personalizadas.

**Funcionalidades demonstradas:**
- Seleção da disciplina com maior dificuldade
- Declaração dos tópicos específicos de dificuldade (solução Cold Start)
- Cálculo e exibição do risco de evasão
- Análise personalizada gerada por IA
- Recomendações de vídeos, PDFs, exercícios, revisões e mapas mentais
- Plano de estudos semanal personalizado

### Pitch Acadêmico
Apresentação interativa com 7 slides navegáveis por teclado (← →) ou clique, cobrindo toda a estrutura pedida pelo professor.

---

## 🚀 Como Executar

### Opção 1 — GitHub Pages (recomendado)
Acesse diretamente pelo link publicado:

```
https://seu-usuario.github.io/sistema-nexus/
```

### Opção 2 — Localmente
Clone o repositório e abra os arquivos no navegador:

```bash
git clone https://github.com/MurilloRigaud/Sistema-Nexus.git
cd Sistema-Nexus
```

Abra o arquivo `pitch-nexus.html` para a apresentação, ou `telas/portal-univerde.html` para a demonstração completa do sistema.

> ⚠️ Para as recomendações geradas por IA funcionarem, o arquivo `nexus-sistema.html` precisa ser acessado via servidor (GitHub Pages ou Live Server). Abertura direta por `file://` pode bloquear a chamada de API por política do navegador.

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Uso |
|---|---|
| HTML5 + CSS3 | Estrutura e estilização de todas as telas |
| JavaScript (Vanilla) | Lógica de navegação, fluxo do sistema e chamadas de API |
| Claude Sonnet API | Geração das análises e recomendações personalizadas em tempo real |
| Google Fonts | Tipografia (Fraunces, DM Sans, Syne) |
| GitHub Pages | Publicação e hospedagem do projeto |

---

## 📚 Referências

- **Andrade et al. (2025).** Evasão em EAD e mineração de dados educacionais.
- **Schein et al. (2002).** Methods and metrics for cold-start recommendations. *ACM SIGIR.*
- **Baker, R. & Yacef, K. (2009).** The state of educational data mining in 2009. *JEDM.*
- **INEP (2023).** Censo da Educação Superior — EAD no Brasil.
- **Chapman et al. (2000).** CRISP-DM 1.0: Step-by-step data mining guide.

---

## 👥 Autores

Trabalho desenvolvido para a disciplina de **Mineração de Dados** — 2026.1

---

<div align="center">

<sub>Desenvolvido como proposta acadêmica · Bloco 3 — Pitch da Ideia e Solução</sub>

</div>