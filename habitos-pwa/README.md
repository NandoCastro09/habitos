# Hábitos 🌿

App de hábitos (PWA): instala no celular, abre em tela cheia e funciona sem internet.
Os dados ficam salvos no próprio celular.

## Estrutura

```
habitos-pwa/
├── index.html             # o app inteiro (HTML + CSS + JS)
├── manifest.webmanifest   # nome, ícone e modo tela cheia
├── sw.js                  # service worker (offline + atualizações)
└── icons/                 # ícones do app
```

## Testar no computador (VS Code)

1. Abra a pasta `habitos-pwa` no VS Code.
2. Instale a extensão **Live Server** (Ritwick Dey).
3. Clique com o botão direito em `index.html` → **Open with Live Server**.

> Abrir o `index.html` com dois cliques também funciona, mas o modo offline
> só liga quando o app roda por `http://` (Live Server ou GitHub Pages).

## Publicar no GitHub Pages

No terminal do VS Code, dentro da pasta:

```bash
git init
git add .
git commit -m "App de hábitos"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/habitos.git
git push -u origin main
```

(Crie antes um repositório **público** vazio chamado `habitos` no GitHub, sem README.)

Depois, no GitHub: **Settings → Pages → Build and deployment**
- Source: **Deploy from a branch**
- Branch: **main** / pasta **/ (root)** → **Save**

Em 1–2 minutos o app fica em: `https://SEU-USUARIO.github.io/habitos/`

## Instalar no celular

- **iPhone:** abra o link no **Safari** → botão Compartilhar → **Adicionar à Tela de Início**.
- **Android:** abra no **Chrome** → vai aparecer **Instalar app** (ou ⋮ → Instalar app).

## Levar os dados da versão do Claude pro app novo

São endereços diferentes, então os dados não passam sozinhos:

1. Na versão antiga (link do Claude): **Ajustes → Copiar backup**.
2. No app instalado: **Ajustes → Restaurar** → cole o texto → **Restaurar**.

## Atualizar o app depois

1. Edite o `index.html`.
2. No `sw.js`, aumente a versão: `habitos-v1` → `habitos-v2`.
3. `git add . && git commit -m "atualização" && git push`

O celular pega a versão nova na próxima vez que abrir o app com internet.

## Observações

- Os dados ficam só no aparelho. Use **Ajustes → Baixar arquivo de backup** de vez em quando.
- O repositório é público: o código (incluindo o recadinho) fica visível; os dados dela, não.
- Lembretes aparecem com o app aberto. Pra alerta com o celular bloqueado, use o botão
  "Adicionar lembrete ao Google Agenda" nos detalhes do hábito.
