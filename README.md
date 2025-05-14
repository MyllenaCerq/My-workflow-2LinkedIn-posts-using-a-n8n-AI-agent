# 🚀 Capiva LinkedIn AI Poster — Automação com n8n

> Automação completa para curadoria, geração e postagem de conteúdos no LinkedIn da página da Capiva usando n8n, RSS, GPT-4o e aprovação humana.

---

## 🧠 Visão Geral

Este projeto automatiza a criação e publicação de posts semanais no LinkedIn da Capiva com as seguintes etapas:

- Coleta de artigos relevantes sobre IA
- Curadoria com IA (seleção dos 5 melhores)
- Geração de texto com linguagem personalizada
- Aprovação humana por email
- Publicação automática no LinkedIn da página Capiva

---

## 🔧 Ferramentas Utilizadas

| Ferramenta           | Finalidade                                                       |
|----------------------|------------------------------------------------------------------|
| [n8n](https://n8n.io) | Orquestrador principal da automação                             |
| OpenAI (GPT-4o)      | Geração de texto com estilo personalizado                        |
| RSS Feed (VentureBeat)| Fonte de notícias da semana                                     |
| Gmail API            | Disparo de aprovação com formulário interativo                  |
| LinkedIn API         | Postagem automática na página da Capiva                         |

---

## 🧱 Arquitetura do Fluxo

1. Trigger manual ou agendado
2. Leitura do RSS de IA (VentureBeat)
3. Curadoria com GPT-4o-mini (seleção dos 5 artigos mais relevantes)
4. Download e extração do conteúdo HTML
5. Resumo dos artigos com CTA para LinkedIn
6. Reescrita no estilo Capiva com IA
7. Envio para aprovação por email
8. Validação condicional:
    - ✅ Se aprovado → publica no LinkedIn
    - ✏️ Se não aprovado → aplica sugestões com IA e reenvia para aprovação
9. Publicação final na página Capiva

---

## 🧩 Detalhes Técnicos

- **ID da página Capiva (LinkedIn):** `106914025`
- **Formato no nó LinkedIn:** `postAs: organization`
- **Campo 'organization' no n8n:** usa apenas o número (não o URN completo)
- **Geração de conteúdo:**  
  - LLM Chain com prompt estruturado  
  - Reescrita em pt-BR com tom conversacional e analítico

---

## 📬 Campos do Formulário de Aprovação

- `Post Validado? ✨` (dropdown: Sim / Não)
- `Alterações Sugeridas 👇` (textarea: texto livre)

---

## ✅ Resultados

- Automação funcional, postando com sucesso na página Capiva
- Controle criativo com validação humana embutida
- Base sólida para escalar e gerar conteúdo consistente

---

## 📌 Futuras Melhorias

- Integração com Slack para alertas pós-publicação
- Registro de posts aprovados em Notion/Airtable
- Geração automática de imagens com DALL·E ou Leonardo
- Agendamento via cron sem trigger manual

---

## 📂 Estrutura do Repositório

/n8n-workflow
├── capiva_linkedin_ai_automation.json
└── README.md

yaml
Copiar
Editar

---

## ✍ Créditos

Desenvolvido por [Myllena Cerqueira](https://www.linkedin.com/in/myllenacerq)  
