#  SuperBanco — Sistema Multiagente com IA
 
**Aluno:** Gabriel De Oliveira Souza &nbsp;|&nbsp; **RM:** 571583 &nbsp;|&nbsp; **Turma:** CCPQ &nbsp;|&nbsp; **FIAP 2026**
 
---
 
## O problema que esse projeto resolve
 
Bancos e fintechs recebem **milhões de atendimentos por dia**. A maioria são perguntas repetitivas sobre tarifas, transferências e saldo — tarefas que não precisam de um humano para resolver, mas que precisam de uma resposta **inteligente, rápida e contextual**.
 
Sistemas de chatbot tradicionais falham porque não conseguem entender linguagem natural e não sabem delegar tarefas para módulos especializados. O resultado: clientes frustrados, filas de atendimento e custo operacional alto.
 
**SuperBanco resolve isso com uma arquitetura multiagente:** cada agente é especialista em uma tarefa, e um roteador inteligente decide — em tempo real — qual deles deve responder. O cliente fala naturalmente. O sistema entende, age e responde.
 
---
 
## 📸 Screenshots
 
### Tela principal
<!-- Print da tela inicial -->
<img width="1363" height="590" alt="tela-principal" src="https://github.com/user-attachments/assets/bd8aa931-d0c3-4f0d-9670-08e6d4642741" />

 
### Agente PIX em ação
<!-- Print de um PIX sendo realizado -->
<img width="1309" height="605" alt="agente-pix" src="https://github.com/user-attachments/assets/4dd526f6-db85-424e-b019-2c0c209e6e16" />

 
### Agente de Dúvidas
<!-- Print do agente respondendo uma dúvida -->
<img width="1308" height="584" alt="agente-duvidas" src="https://github.com/user-attachments/assets/a6b88fef-95a1-4c0a-ab89-d6dc50923d98" />

 

---
 
## O que foi construído
 
Um sistema de atendimento bancário com **3 agentes de IA especializados** que colaboram entre si. A partir de uma mensagem em linguagem natural como *"Faça um PIX de R$ 50 para a Ana"*, o sistema:
 
1. Identifica a intenção do usuário
2. Faz o **handoff** para o agente correto
3. O agente executa as **ferramentas** necessárias
4. Retorna uma resposta clara e contextual
Tudo isso sem que o usuário precise navegar por menus ou seguir scripts rígidos.
 
---
 
##  Arquitetura Multiagente
 
```
Usuário
   │
   ▼
Agente Roteador
   │
   ├── intent: "pix"     ──▶  Agente PIX
   │                           ├── tool: buscarContato()
   │                           ├── tool: verificarSaldo()
   │                           └── tool: executarPix()
   │
   ├── intent: "saldo"   ──▶  Agente PIX
   │                           └── tool: verificarSaldo()
   │
   └── intent: "duvidas" ──▶  Agente de Dúvidas
                               └── base de conhecimento do banco
```
 
### Agentes
 
| Agente | Responsabilidade |
|---|---|
|  **Roteador** | Classifica a intenção e faz o handoff para o especialista |
|  **Atendimento** | Responde mensagens gerais e orienta o usuário |
|  **Agente PIX** | Busca contatos, valida saldo e executa transferências |
|  **Agente de Dúvidas** | Responde sobre tarifas, produtos e serviços com histórico de conversa |
 
### Ferramentas (Tools)
 
| Tool | O que faz |
|---|---|
| `buscarContato(nome)` | Busca na lista de contatos por nome parcial |
| `verificarSaldo()` | Retorna o saldo disponível da conta |
| `executarPix(contato, valor)` | Valida e executa a transferência, atualizando o saldo |
 
---
 
## Por que isso importa para empresas
 
> *"Até 2026, 85% das interações com clientes serão gerenciadas sem um agente humano."*  
> — Gartner
 
Arquiteturas multiagente com LLMs estão no centro da transformação digital de bancos, fintechs, e-commerce e saúde. Empresas como **Nubank, Itaú, Inter e iFood** já investem pesado em sistemas exatamente como esse — onde agentes de IA colaboram para resolver problemas complexos de forma autônoma.
 
As habilidades demonstradas nesse projeto — **orquestração de agentes, integração com LLMs via API, design de ferramentas e handoffs** — são as mesmas que essas empresas buscam em desenvolvedores juniores e estagiários de IA hoje.
 
---
 
##  Tecnologias
 
- **React 18** + **Vite 5**
- **Anthropic API** 
- Arquitetura: Agents + Tools + Handoffs
- CSS-in-JS com design tokens
- Fontes: Plus Jakarta Sans + Inter + JetBrains Mono
---
 
##  Conceitos aplicados
 
- **Agents** — cada agente tem system prompt e escopo de atuação próprios
- **Tools** — funções que os agentes chamam para executar ações reais no sistema
- **Handoffs** — delegação de tarefas entre agentes com base na intenção detectada
- **Histórico de conversa** — o Agente de Dúvidas mantém contexto entre turnos
- **Prompt engineering** — instruções precisas para extração de entidades (nome, valor) em JSON
 
---
 
## 💬 Exemplos de uso
 
| Mensagem do usuário | Agente ativado |
|---|---|
| `"Faça um PIX de R$ 50 para a Ana"` | 💸 Agente PIX |
| `"Qual meu saldo?"` | 💸 Agente PIX |
| `"Tem taxa pra usar o PIX à noite?"` | ❓ Agente de Dúvidas |
| `"Qual a anuidade do cartão?"` | ❓ Agente de Dúvidas |
 
---
 
##  Como rodar
 
### 1. Clonar o repositório
 
```bash
git clone https://github.com/seu-usuario/banco-multiagente.git
cd banco-multiagente
```
 
### 2. Instalar dependências
 
```bash
npm install
```
 
### 3. Configurar a chave da API
 
```bash
cp .env.example .env
```
 
Abra o `.env` e adicione sua chave:
 
```
VITE_ANTHROPIC_KEY=sk-ant-sua-chave-aqui
```
 
 
### 4. Rodar
 
```bash
npm run dev
```
 
Acesse **http://localhost:5173**
