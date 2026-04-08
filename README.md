# flat.notes

Daily note-taking app com integração Google Calendar.

## setup em 5 passos

### 1. Google Cloud Console

1. Acesse [console.cloud.google.com](https://console.cloud.google.com)
2. Crie um projeto novo
3. **APIs & Services → Library** → busca `Google Calendar API` → Enable
4. **APIs & Services → OAuth consent screen**
   - User Type: External
   - Preenche nome e email
   - Scopes: adiciona `https://www.googleapis.com/auth/calendar.readonly`
   - Test users: adiciona seu email
5. **Credentials → Create Credentials → OAuth Client ID**
   - Application type: **Web application**
   - Authorized JavaScript origins: `https://wes-dot.github.io`
   - Authorized redirect URIs: `https://wes-dot.github.io/flat-notes/`
6. Copia o **Client ID**

### 2. Configure o app

Abre `index.html` e troca na linha do CLIENT_ID:

```js
const CLIENT_ID = 'SEU_CLIENT_ID_AQUI';
```

por:

```js
const CLIENT_ID = '1234567890-abc...apps.googleusercontent.com';
```

### 3. Sobe no GitHub

```bash
git init
git add index.html
git commit -m "flat notes inicial"
git remote add origin https://github.com/SEU-USUARIO/flat-notes.git
git push -u origin main
```

### 4. Ativa o GitHub Pages

No repositório → **Settings → Pages → Source: main branch → / (root)** → Save

Seu app fica em: `https://SEU-USUARIO.github.io/flat-notes/`

---

## prefixos

| símbolo | significado |
|---------|-------------|
| `!` | prioridade alta |
| `-` | tarefa normal |
| `~` | em progresso / bloqueado |
| `@` | incidente ocorrido |
| `>` | ideia / insight |
| `?` | dúvida pra pesquisar |
| `*` | aprendizado (GCP, AWS...) |

## funcionalidades

- notas diárias com prefixos visuais
- filtro por tipo de nota
- vincular nota a evento do Google Calendar
- histórico dos últimos 7 dias
- exportar o dia como `.md`
- tudo salvo localmente no browser
