# AgendCS — Deploy no Vercel
## Guia completo: do arquivo local ao site publicado

---

## ✅ O QUE VOCÊ TEM NESTA PASTA

| Arquivo | Descrição |
|---|---|
| `index.html` | Aplicação completa (todos os dados embutidos) |
| `vercel.json` | Configuração de roteamento do Vercel |
| `.gitignore` | Ignora arquivos desnecessários no Git |

---

## 🚀 PASSO A PASSO — DEPLOY EM 10 MINUTOS

### ETAPA 1 — Criar conta no GitHub (gratuito)
1. Acesse **github.com**
2. Clique em **Sign up** → crie com seu e-mail
3. Confirme o e-mail recebido

---

### ETAPA 2 — Criar repositório no GitHub
1. Clique no **+** (canto superior direito) → **New repository**
2. Nome: `agendcs` (ou qualquer nome)
3. Visibilidade: **Private** (recomendado)
4. Clique em **Create repository**

---

### ETAPA 3 — Subir os arquivos para o GitHub
Opção A — pelo site (mais fácil, sem instalar nada):
1. Na página do repositório criado, clique em **uploading an existing file**
2. Arraste os 3 arquivos desta pasta:
   - `index.html`
   - `vercel.json`
   - `.gitignore`
3. Clique em **Commit changes**

Opção B — pelo terminal (se tiver Git instalado):
```bash
git init
git add .
git commit -m "AgendCS deploy"
git remote add origin https://github.com/SEU_USUARIO/agendcs.git
git push -u origin main
```

---

### ETAPA 4 — Criar conta no Vercel (gratuito)
1. Acesse **vercel.com**
2. Clique em **Sign Up** → escolha **Continue with GitHub**
3. Autorize o Vercel a acessar seus repositórios

---

### ETAPA 5 — Publicar no Vercel
1. No Vercel, clique em **Add New → Project**
2. Selecione o repositório `agendcs`
3. Em **Framework Preset** → selecione **Other**
4. Clique em **Deploy**
5. Aguarde ~30 segundos

**Resultado:** URL gerada automaticamente, exemplo:
```
https://agendcs-squad1.vercel.app
```

---

### ETAPA 6 — (Opcional) Personalizar a URL
1. No Vercel → Settings → Domains
2. Clique em **Edit** no domínio padrão
3. Digite o nome desejado, ex: `agendcs-gtplan`
4. Nova URL: `https://agendcs-gtplan.vercel.app`

---

## 🔐 CREDENCIAIS DE ACESSO

| Campo | Valor |
|---|---|
| Login | cs.squad1@gtplan.com.br |
| Senha | CS.SQUAD1 |
| Perfil | Editor (acesso completo) |

Qualquer pessoa sem login acessa como **Visitante** (somente leitura).

---

## 💾 COMO OS DADOS FUNCIONAM

```
┌─────────────────────────────────────────┐
│  Primeira abertura do site              │
│                                         │
│  1. Tenta carregar da nuvem             │
│     (window.storage compartilhado)      │
│                                         │
│  2. Se nuvem vazia → usa backup         │
│     embutido no index.html              │
│     (dados do dia 21/03/2026)           │
│                                         │
│  3. Salva na nuvem automaticamente      │
│     → todos os usuários sincronizados   │
└─────────────────────────────────────────┘
```

- **Edições** são salvas automaticamente na nuvem a cada 2 segundos
- **Todos os dispositivos** veem os mesmos dados em tempo real
- **Polling** verifica atualizações a cada 15 segundos
- **Fallback** para localStorage se nuvem estiver indisponível

---

## 🔄 COMO ATUALIZAR O SITE (futuras versões)

1. Substitua o `index.html` no repositório GitHub
2. O Vercel detecta a mudança e republica automaticamente
3. Em ~30 segundos o site está atualizado

No GitHub: abra o arquivo → clique no lápis (editar) → cole o novo conteúdo → Commit.

---

## 📱 RESPONSIVIDADE

O site funciona em:
- ✅ Desktop (Chrome, Edge, Firefox, Safari)
- ✅ Tablet
- ✅ Smartphone (barra de navegação inferior automática)

---

## 🛡️ BACKUP DOS DADOS

Para exportar um backup a qualquer momento:
1. Faça login no site
2. Vá em **Configurações → Parâmetros do Sistema**
3. Clique em **Download Backup JSON**
4. Guarde o arquivo gerado

---

## ⚡ ALTERNATIVA MAIS RÁPIDA — NETLIFY DROP

Se não quiser criar conta no GitHub:

1. Acesse **app.netlify.com/drop**
2. Arraste o arquivo `index.html` para a tela
3. Em 10 segundos você tem uma URL funcionando

> ⚠️ Atenção: no Netlify Drop os dados ficam no localStorage local de cada navegador
> (não são compartilhados entre dispositivos automaticamente).
> Para dados 100% compartilhados, use o Vercel + GitHub conforme acima.

---

## 📞 RESUMO DOS LINKS NECESSÁRIOS

| Serviço | URL | Gratuito |
|---|---|---|
| GitHub | github.com | ✅ |
| Vercel | vercel.com | ✅ |
| Netlify (alternativa) | app.netlify.com/drop | ✅ |

---

*AgendCS v11.2.0 — Squad 1 — GTPlan*
