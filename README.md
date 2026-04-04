# n8n-ai-financial-agent
Sistema multi-agentes de atendimentovia telegram financeiro automatizado usando n8n e Google Gemini
<img width="1785" height="740" alt="image" src="https://github.com/user-attachments/assets/eaca5491-ef8d-49f2-a6a1-0b6be108b612" />



## 📌 Sobre o Projeto
Este projeto é um sistema automatizado de triagem e atendimento ao cliente construído com a arquitetura de **Agentic Workflow** (Múltiplos Agentes Especialistas). Ele opera via Telegram e utiliza a inteligência da API do Google Gemini para ler, interpretar (texto e áudio) e rotear o usuário para o departamento correto de forma 100% autônoma.

O objetivo do projeto é acabar com a dependência de um único prompt gigante e dividir a "inteligência" em pequenos robôs especialistas, aumentando a precisão e velocidade do atendimento.

## 🏗️ Como a Arquitetura Funciona
1. **Gatilho (Telegram):** O cliente envia uma mensagem de texto ou áudio.
2. **Transcrição de Áudio:** Se for áudio, o sistema faz o download e usa o modelo `gemini-2.5-flash` para transcrever para texto.
3. **Agente Gerente (Sofia):** Uma IA central analisa a intenção do cliente e decide qual sub-agente acionar.
4. **Sub-Agentes Especialistas:**
   - 📞 **Agente de Suporte (Leo):** Responde dúvidas técnicas de forma didática.
   - 📅 **Agente de CS / Qualificação (Arthur):** Interage com o cliente e agenda reuniões diretamente no **Google Calendar**.
   - 💰 **Agente Financeiro (Bia):** Consulta status de pagamentos de boletos conectando-se a uma base de dados no **Google Sheets**.
5. **Retorno:** A resposta processada pelo especialista é devolvida ao cliente no Telegram.

## 🚀 Tecnologias Utilizadas
- **[n8n](https://n8n.io/):** Orquestração do fluxo, webhooks e integração de APIs.
- **Google Gemini API:** LLM utilizado para processamento de linguagem natural e transcrição.
- **Telegram Bot API:** Interface de comunicação com o usuário final.
- **Google Workspace APIs:** Integração com Google Sheets (simulando um Banco de Dados) e Google Calendar.


## 💡 Aprendizados
Este projeto me permitiu entender na prática como integrar LLMs com plataformas de automação (n8n), tratar respostas em JSON, estruturar prompts baseados em papéis e integrar múltiplos serviços usando requisições HTTP e APIs de terceiros.
