# 📚 Documentação de Workflows n8n com Agentes de IA

## 🎯 Sobre o Projeto
Este repositório contém automações avançadas desenvolvidas no [n8n](https://n8n.io), focadas na criação de **Agentes de Inteligência Artificial** autônomos com memória de contexto e capacidade de uso de ferramentas externas (Tool Calling).

Cada workflow é estruturado com os seguintes componentes principais:

| Componente | Descrição |
|-----------|-----------|
| **⚡ Trigger** | Eventos que iniciam o fluxo (Webhooks ou Chat Web nativo) |
| **🧠 Agente IA** | Modelos LLM de alta performance tomando decisões e formatando respostas |
| **🔧 Actions** | Tarefas executadas em resposta (operações em planilhas, consultas na web, requisições HTTP) |

---

## 🤖 Os Agentes Desenvolvidos

### 1️⃣ Agente Web (Suporte e Registro de Interações)
Um agente de IA focado em atendimento direto, acessível via link web público.
* **Como funciona:** O usuário envia uma dúvida ➡️ O fluxo salva a pergunta no Google Sheets (para auditoria) ➡️ O Agente processa a resposta usando memória e ferramentas (Wikipedia/Calculadora) ➡️ Responde na interface de chat.

### 2️⃣ Agente WhatsApp (Captação de Leads Inteligente)
Um agente integrado ao WhatsApp (via Z-API), projetado para qualificação de contatos 1 a 1.
* **Como funciona:** Recebe a mensagem via Webhook ➡️ Passa por um **filtro lógico (Node IF)** que ignora grupos e listas de transmissão ➡️ Extrai o Nome e Telefone do usuário ➡️ Atualiza a planilha de Leads no Google Sheets (evitando contatos duplicados) ➡️ O Agente gera a resposta ➡️ O fluxo faz um `POST` devolvendo a mensagem para o WhatsApp do cliente.

---

## 🚀 Como Usar os Workflows

Siga estes passos para testar os fluxos no seu próprio ambiente:

1. 📦 Clone este repositório ou faça o download dos arquivos `.json`.
2. 📥 Importe o workflow desejado na sua instância do n8n (`Workflows > Import from File`).
3. ⚙️ Ajuste as credenciais de segurança:
   * **Groq API:** Insira sua chave para habilitar o modelo LLM.
   * **Google Sheets:** Autentique sua conta e mapeie o ID da sua planilha.
   * **Z-API:** (Apenas Workflow 2) Insira seu Token e URL da instância no nó de HTTP Request.
4. ▶️ Dispare o workflow manualmente para testar ou ative-o (Active) para rodar em background.

---

## 🔌 Integrações Utilizadas

Estes workflows demonstram a integração fluida entre as seguintes tecnologias:

- **🌐 Groq API**: Processamento de IA em tempo real usando o modelo `llama-3.3-70b-versatile`.
- **🗄️ Google Sheets**: Atuando como banco de dados leve para registro de logs e CRM de leads.
- **📱 Z-API**: Comunicação bidirecional com o WhatsApp.
- **🛠️ LangChain Tools**: Ferramentas nativas de IA do n8n para buscar dados precisos fora do modelo.

---

## 🤝 Guia de Contribuição

Contribuições são muito bem-vindas! Para contribuir:

1. 🍴 Faça um fork do repositório
2. 🌿 Crie uma branch para sua feature (`git checkout -b feature/SuaFeature`)
3. ✏️ Faça suas alterações e commit (`git commit -m 'Adiciona nova feature'`)
4. 📤 Envie para a branch (`git push origin feature/SuaFeature`)
5. 🔄 Abra um Pull Request explicando suas mudanças

**Obrigado por contribuir!** 🎉
