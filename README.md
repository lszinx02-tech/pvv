# Agenda CLV

Agenda de manutenção para oficina. Funciona sozinha: sem login, sem nuvem e sem inteligência artificial.
Os dados ficam **criptografados (AES-256) no IndexedDB do próprio aparelho**, protegidos por uma senha que você cria.

## Estrutura
- `index.html`, `css/app.css`, `js/app.js` (telas e regras), `js/storage.js` (IndexedDB, senha, criptografia, backup)
- `manifest.webmanifest`, `sw.js`, `icons/` (instalação e uso offline)
- Não há dependências: não precisa de `npm install`.

## Rodar no computador (VS Code)
1. Instale o Node.js 18+ (nodejs.org). Abra a pasta no VS Code e o terminal (Ctrl+`).
2. `npm start`
3. Abra http://localhost:8080 no Chrome. (Alternativa sem Node: `python -m http.server 8080`.)
4. Verificar a sintaxe: `npm run check`

Importante: a senha e o offline só funcionam em `localhost` ou `https`. Abrir o arquivo com duplo clique não funciona.

## Publicar de graça (escolha uma)
- **Netlify Drop:** acesse app.netlify.com/drop e arraste a pasta inteira. Você recebe um link https.
- **Cloudflare Pages** (Upload direto) ou **GitHub Pages:** envie a pasta e ative o Pages.
Depois de publicado, o app não depende do seu computador nem do Claude.

## Instalar no celular
- **Android (Chrome):** abra o link, toque em ⋮ → "Instalar app" / "Adicionar à tela inicial".
- **iPhone (Safari):** abra o link, toque em Compartilhar → "Adicionar à Tela de Início". Use sempre pelo ícone instalado.

## Senha e backup
- Primeiro acesso: crie a senha. **Sem a senha não há como recuperar os dados.**
- ⚙ Ajustes → "Fazer backup" gera um arquivo .json (continua criptografado). Guarde no Drive, e-mail ou WhatsApp.
- "Restaurar backup" substitui os dados; você entra com a senha que o backup tinha.
- Dados são por aparelho. O iPhone pode apagar dados de sites não instalados após dias sem uso: instale o app e faça backups.

## Atualizar depois de editar o código
Mude `const V='clv-v1'` em `sw.js` (ex.: `clv-v2`) e publique de novo, para os celulares baixarem a versão nova.
