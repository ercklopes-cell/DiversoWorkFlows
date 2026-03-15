# Diverso WorkFlows Management

Organizador de projetos para criativos e empreendedores com Brainstorm visual, Editor de Prompts, Kanban, Fluxograma e integração com IA (GPT-4 Mini via GitHub Models / OpenAI).

---

## 📁 Estrutura do Projeto

```
diverso-project/
├── public/
│   ├── index.html      ← Landing page (tela de entrada)
│   └── app.html        ← Aplicativo principal
├── vercel.json         ← Configuração de deploy no Vercel
└── README.md
```

---

## 🚀 Deploy no Vercel

### Opção 1 — Via GitHub (recomendado)

1. Suba este repositório no GitHub
2. Acesse [vercel.com](https://vercel.com) → **Add New Project**
3. Conecte o repositório do GitHub
4. Clique em **Deploy** — pronto!

O Vercel detecta automaticamente o `vercel.json` e serve os arquivos da pasta `public/`.

### Opção 2 — Upload direto

1. Acesse [vercel.com](https://vercel.com)
2. Arraste a pasta `diverso-project/` para o dashboard
3. Aguarde o deploy

---

## 🔑 Configurar Login com Google (OAuth)

Após ter o domínio no Vercel (ex: `diverso-project.vercel.app`):

### Passo 1 — Google Cloud Console

1. Acesse [console.cloud.google.com](https://console.cloud.google.com)
2. Crie um novo projeto
3. Vá em **APIs & Services → OAuth consent screen**
   - User Type: **External**
   - Preencha nome do app e e-mail de suporte
4. Vá em **APIs & Services → Credentials → Create Credentials → OAuth 2.0 Client ID**
   - Application type: **Web application**
   - **Authorized JavaScript origins:**
     ```
     https://SEU-PROJETO.vercel.app
     http://localhost (para testes locais)
     ```
   - **Authorized redirect URIs:**
     ```
     https://SEU-PROJETO.vercel.app
     http://localhost
     ```
5. Copie o **Client ID** gerado (formato: `xxxxxxx.apps.googleusercontent.com`)

### Passo 2 — Inserir no código

No arquivo `public/index.html`, localize o comentário:
```
<!-- GOOGLE_CLIENT_ID -->
```
E substitua `YOUR_CLIENT_ID` pelo seu Client ID real.

---

## 🤖 Configurar IA (GitHub Models / OpenAI)

1. Abra o app em `app.html`
2. Clique em **☰ → Configurações**
3. Cole seu token em **Token GitHub / API Key**
4. Selecione o modelo desejado (`gpt-4o-mini` recomendado)
5. Clique em **Salvar**

**Para obter o token do GitHub Models:**
- Acesse [github.com/settings/tokens](https://github.com/settings/tokens)
- Gere um token com permissão de leitura
- Use como API Key no app

---

## ✨ Funcionalidades

| Módulo | Descrição |
|--------|-----------|
| 💡 Brainstorm | Post-its coloridos conectáveis com undo (Ctrl+Z) |
| ✍️ Editor de Prompts | Múltiplos editores com histórico de versões |
| 📋 Kanban | 3 colunas drag-and-drop com botões ↑ ↓ 🗑 |
| 🔀 Fluxograma | Visual automático editável por texto |
| 📁 Arquivos | Pastas virtuais com notas por projeto |
| 🤖 IA | Organiza projetos via GPT-4 Mini automaticamente |

---

## 💾 Dados

- Todos os dados ficam salvos no **localStorage** do navegador
- Nenhum servidor ou banco de dados necessário
- Use **Exportar** nas configurações para fazer backup em JSON

---

## 🛠 Tecnologias

- HTML5 + CSS3 + JavaScript vanilla
- Google Fonts (Orbitron + DM Sans)
- localStorage para persistência
- Google Identity Services (OAuth 2.0)
- OpenAI / GitHub Models API

---

*Diverso Project © 2026 — Feito para criativos que pensam rápido*
