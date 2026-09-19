# Juristas de Programa — Site institucional

Site estático (HTML + CSS + JS puro, sem frameworks) do projeto de extensão Juristas de Programa (UESC).

## Estrutura

```
site/
├── index.html          → página principal
├── coordenadores.html  → página dos coordenadores (aberta pelo menu da logo)
├── imagens/             → todas as imagens do site
└── README.md
```

## Como visualizar

Basta abrir `index.html` diretamente no navegador. Não precisa de servidor nem instalação.

## Onde alterar cada coisa

Tudo fica dentro da tag `<style>` de cada arquivo HTML (sem CSS externo, por ainda serem só 2 páginas).

- **Cores e espaçamentos**: no bloco `:root { ... }` no topo do `<style>`. Ex: mudar `--color-primary` muda o azul principal em várias partes do site de uma vez.
- **Textos das seções**: direto no HTML, dentro de `<main>`.
- **Logos do rodapé**: procure por `.footer-logos` no `index.html`. Cada logo é um `<a class="footer-logo-link">` com uma `<img>` dentro. Todas usam o mesmo "slot" de tamanho fixo (`.footer-logo-link`), então uma logo nova automaticamente fica do mesmo tamanho das outras — só trocar o `src`, `href` e `alt`.
- **Coordenadores / novos integrantes**: em `coordenadores.html`, dentro de `.members-grid`. Cada pessoa é um bloco `<article class="member-card">` — copie um bloco existente e troque foto, nome e cargo para adicionar alguém novo.
- **Menu da logo (nav)**: o dropdown com "Coordenadores" está no `<script>` do `index.html`, próximo ao HTML da `.nav-logo-wrapper`. Para adicionar uma nova opção no menu, basta adicionar outro `<a role="menuitem">` dentro de `.nav-dropdown`.

## Imagens

Coloque novas imagens em `imagens/`. Prefira PNG com fundo transparente para logos, e JPEG para fotos de pessoas.

## Observações

- Os links de `og:image`/`twitter:image` e o `canonical` usam uma URL placeholder (`juristasdeprograma.uesc.br`). Troque pelo domínio real assim que o site for publicado.
- O chatbot no Telegram está marcado como "em construção" — quando estiver pronto, troque o bloco `.aviso-construcao` por um botão `<a>` linkando para o bot (há um exemplo comentado no histórico de versões anteriores).
