# 💳 SuperBanco — Sistema Multiagente com IA

**Projeto Final · Fundamentos de IA e Programação Web**
Aluno: Gabriel Silva | RM: 12345 | Turma: 2TDSA | FIAP 2026

---

## 📋 Sobre o projeto

Sistema de atendimento bancário inteligente com múltiplos agentes de IA que colaboram entre si usando os conceitos de **Agents**, **Tools** e **Handoffs**.

### Agentes implementados

| Agente | Função |
|---|---|
| 🏦 **Roteador** | Recebe a mensagem e decide qual agente especializado deve responder |
| 💸 **Agente PIX** | Busca contatos, verifica saldo e realiza transferências simuladas |
| ❓ **Agente de Dúvidas** | Responde perguntas sobre produtos, tarifas e serviços do banco |

### Ferramentas (Tools)

- `buscarContato(nome)` — procura na lista de contatos cadastrados
- `verificarSaldo()` — retorna o saldo atual da conta
- `executarPix(contato, valor)` — realiza a transferência e atualiza o saldo

---

## 🚀 Como rodar

### 1. Instalar dependências

```bash
npm install
```

### 2. Configurar a chave da API

Crie um arquivo `.env` na raiz do projeto (copie o `.env.example`):

```bash
cp .env.example .env
```

Abra o `.env` e coloque sua chave da API da Anthropic:

```
VITE_ANTHROPIC_KEY=sk-ant-sua-chave-aqui
```

> Pegue sua chave gratuita em: https://console.anthropic.com

### 3. Rodar o projeto

```bash
npm run dev
```

Abra o navegador em **http://localhost:5173**

---

## 📁 Estrutura do projeto

```
banco-multiagente/
├── src/
│   ├── App.jsx       ← componente principal (agentes + UI)
│   └── main.jsx      ← entrada do React
├── index.html
├── package.json
├── vite.config.js
├── .env              ← sua chave da API (não sobe pro GitHub!)
├── .env.example      ← modelo do .env
└── .gitignore
```

---

## 💬 Exemplos de uso

- `"Faça um PIX de R$ 50 para a Ana"`
- `"Qual meu saldo?"`
- `"Tem taxa pra usar o PIX à noite?"`
- `"Manda R$ 200 pro Pedro"`
- `"Qual a anuidade do cartão?"`

---

## 🛠️ Tecnologias

- **React 18** + **Vite**
- **API Anthropic** (Claude claude-sonnet-4-6)
- CSS-in-JS com design tokens
- Fontes: Plus Jakarta Sans + Inter + JetBrains Mono
