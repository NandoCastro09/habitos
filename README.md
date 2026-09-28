# Hábitos 🌿

Fiz esse app pra Mariana acompanhar os hábitos dela. É um app web que dá pra
instalar no celular e usar como se fosse um app normal: abre em tela cheia,
tem ícone próprio e funciona até sem internet.

Link: https://nandocastro09.github.io/habitos/

## O que tem nele

- Hábitos por dia da semana, com meta (tipo 8 copos de água) e horário
- Hábitos pra evitar (ex: não roer as unhas), que contam como feitos até você marcar um deslize
- Sequências, desafios de 21/30/66 dias e conquistas
- Timer pra hábitos com tempo (meditar, estudar...)
- Diário com humor do dia
- Gráficos de progresso e uma plantinha que vai crescendo conforme você usa
- Tema claro/escuro e algumas cores pra escolher

## Como instalar no celular

No iPhone, abre o link no Safari, toca no botão de compartilhar e depois em
"Adicionar à Tela de Início".

No Android, abre no Chrome e toca em "Instalar app" (se não aparecer, tá no menu ⋮).

Depois é só usar pelo ícone. Os dados ficam salvos no próprio celular, então
não precisa de conta nem login. Mas de vez em quando vale fazer um backup em
Ajustes, porque se apagar o app ou limpar os dados do navegador, perde tudo.

## Arquivos

```
index.html            o app inteiro (HTML, CSS e JS num arquivo só)
manifest.webmanifest  nome, ícone e configuração pra instalar
sw.js                 service worker, é o que faz funcionar offline
icons/                ícones
```

## Rodando localmente

Abri no VS Code com a extensão Live Server (botão direito no `index.html` →
Open with Live Server). Abrir o arquivo direto também funciona, só que aí o
modo offline não liga.

## Atualizando

Sempre que mexer no código, lembrar de trocar a versão no começo do `sw.js`
(`habitos-v2` → `habitos-v3` e assim vai). Se não trocar, o celular continua
usando a versão antiga que ficou salva.

```bash
git add .
git commit -m "o que mudou"
git push
```

O GitHub Pages atualiza sozinho em 1 ou 2 minutos, e o app pega a versão nova
na próxima vez que for aberto com internet.

## Limitações

Lembrete com o celular bloqueado não rola, porque app web não consegue mandar
notificação desse jeito. Os lembretes aparecem com o app aberto, e nos detalhes
de cada hábito tem um botão pra jogar o lembrete pro Google Agenda.
