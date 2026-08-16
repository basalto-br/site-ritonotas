# Site — landing page do produto

Landing de uma página, estática, para o produto de controle de protocolos de atos notariais.
Repositório separado da ferramenta. Publica na Cloudflare Pages em `ritonotas.com.br`.

## Contexto de marca (decidido em agosto de 2026)

Três camadas, e elas não se misturam:

- **Basalto** — o studio. Marca-mãe, institucional. Aparece só no rodapé e em contrato.
  Posicionamento: "ferramentas novas que viram rotina". Paleta acromática, cinzas frios.
- **Rito** — a linha de produtos para cartório. Marca a registrar no INPI, classe 42, nominativa.
- **Rito Notas** — este produto. Falado "o Rito". Domínio `ritonotas.com.br`.

**Atenção:** o nome ainda diz "Controle de Atos" no conteúdo desta página, de propósito.
A troca para Rito depende de uma verificação da marca RITO no INPI (processo 906538793),
marcada para 6 de outubro de 2026. Não renomeie nada antes disso.

## Escopo do produto — não errar isso

O Rito Notas **não substitui** sistema de cartório (DRD, Escriba, CartSys, Acsiv).
Não faz lavratura de ato, emissão de selo nem cartão de firma.

Ele controla o **andamento do trabalho**: prazo, responsável, próximo passo, checklist
de documentos por tipo de ato.

**O concorrente real é a planilha, o caderno e o papel na mesa.** A landing tem um bloco
de escopo logo abaixo dos botões dizendo isso — ele é argumento de venda, não ressalva.
Não remova nem enfraqueça.

## Stack e restrições

- **Arquivo único `index.html`.** HTML + CSS inline, **sem JavaScript**, sem build, sem framework.
- Única dependência externa: Google Fonts (Source Serif 4, Inter, JetBrains Mono).
- Alvo de peso: manter abaixo de ~20 KB. Internet ruim de cartório é risco documentado
  no plano de lançamento — a página tem que abrir instantânea.
- Não introduza bundler, framework, gerador de site estático ou dependência npm.

## Sistema visual

Herdado da ferramenta (`../controle-atos-cartorio/controle-atos.html`). Estética de papel,
tinta e carimbo. Não invente cor nova; use as variáveis já definidas no `:root`.

| Token | Valor | Uso |
|---|---|---|
| `--bg` | `#EFECE1` | fundo, bege papel |
| `--card` / `--ficha` | `#FBFAF6` / `#FFFEFA` | superfícies |
| `--ink` | `#221F1A` | texto principal |
| `--ink-med` / `--ink-soft` | `#3F3C34` / `#57544B` | texto secundário |
| `--line` / `--borda` | `#D9D4C6` / `#E0DCCE` | bordas |
| `--carimbo` | `#8C2A20` | acento, botão primário, selo |

Fontes: Source Serif 4 nos títulos, Inter no corpo, JetBrains Mono nas etiquetas.

**Esta paleta é do produto, não da Basalto.** A Basalto é acromática (cinzas de basalto
mais acento ciano `#3FA7C4` sobre escuro / `#17677D` sobre claro). Não misture as duas.

## Acessibilidade — já verificada, não regrida

Todos os pares de contraste foram medidos e passam WCAG AA. O pior está em 5,94:1.

Ao mexer em cor ou tamanho, mantenha:

- Contraste mínimo de 4,5:1 em texto normal
- Botões com altura mínima de 48px
- Link "pular para o conteúdo" no topo
- `:focus-visible` com contorno visível
- `prefers-reduced-motion` respeitado
- Alt text descritivo em toda imagem

## Deploy

Cloudflare Pages conectado a este repositório.

- Build command: nenhum
- Build output directory: `/` (raiz)
- Production branch: `main`
- Domínio: `ritonotas.com.br`
- A ferramenta em si vai para `app.ritonotas.com.br`, projeto separado. Não misture os dois.

### Branches

| Branch | Papel | Onde publica |
|---|---|---|
| `main` | produção | `ritonotas.com.br` |
| `dev` | teste | preview automático `.pages.dev` |

**`main` não recebe commit direto — só merge de `dev`.** Toda alteração nasce em `dev`,
é conferida no preview, e só então vai para `main`.

## Pendências antes de publicar

Procure por `TROCAR` no `index.html`. **Faltam duas:**

1. **Número do WhatsApp** — 3 ocorrências, todas com o número de exemplo
   `5527000000000`.
2. **`img/tela-lista.png`** — a captura não existe, e o `index.html` já a referencia:
   hoje a imagem da dobra principal **quebra**. Exportar da ferramenta **sem nenhum
   dado real de cliente**; ver `img/LEIA-ME.md`.

**Resolvidas — não refaça:**

- **E-mail de contato** → `contato@ritonotas.com.br`, no `href` do `mailto` e no texto
  visível.
- **Razão social e CNPJ** → a linha do rodapé foi **removida**. Volta quando o CNPJ
  existir; o comentário no lugar dela diz isso.
- **Links de Política de Privacidade e Termos de Uso** → **removidos do rodapé**.
  Apontavam para `politica-de-privacidade.html` e `termos-de-uso.html`, que não existem
  no repositório — em produção seriam dois 404 em toda página. Repor junto com as
  páginas.
- **A palavra "livro"** saiu do `<title>`, do subtítulo da dobra e do rodapé, pela regra
  de terminologia em "O que não fazer".

## Sem seção de autoria — e é deliberado

A página não apresenta quem a fez, e isso é uma decisão, não um esquecimento.
**Não crie uma seção de autoria sem pedido explícito.**

Não adicione foto, nome, biografia nem qualquer informação profissional do autor, e não
escreva de memória nada a respeito dele. Se surgir a necessidade, pergunte antes.

## O que não fazer

- Não adicionar JavaScript sem necessidade real
- Não adicionar formulário de captura — o CTA é WhatsApp e teste direto da ferramenta
- Não incluir depoimento, contador de clientes ou selo de "anos de mercado" — não existem
- Não usar emoji nem superlativo. O comprador é tabelião; sobriedade é o ativo
- Não usar a palavra "livro" para descrever a ferramenta: em serventia é termo de arte
  com peso legal (Livro de Notas, Livro Protocolo) e cria ambiguidade sobre escopo
- Não commitar dado real de protocolo, cliente ou serventia, em nenhuma branch
