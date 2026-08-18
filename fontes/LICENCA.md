# Fontes servidas por este domínio

As três famílias abaixo são redistribuídas aqui em arquivo `.woff2`, subconjunto latino,
em versão variável — um arquivo por família cobre toda a faixa de peso.

| Arquivo | Família | Autoria | Licença |
|---|---|---|---|
| `inter.woff2` | Inter | Rasmus Andersson | SIL Open Font License 1.1 |
| `source-serif-4.woff2` | Source Serif 4 | Frank Grießhammer / Adobe | SIL Open Font License 1.1 |
| `jetbrains-mono.woff2` | JetBrains Mono | JetBrains | SIL Open Font License 1.1 |

A SIL OFL 1.1 permite uso, estudo, modificação e redistribuição, inclusive comercial,
desde que os arquivos de fonte não sejam vendidos isoladamente e que o aviso de licença
acompanhe a redistribuição. É o que este arquivo faz.

Texto integral da licença: <https://openfontlicense.org>

## Por que estão aqui

Até 18/08/2026 a landing carregava estas fontes do Google Fonts. Cada visitante entregava
IP e User-Agent a um terceiro, sem escolha — incoerente numa página cujo argumento central
é que o dado do cartório não sai do lugar.

São os mesmos arquivos já embutidos em base64 no `controle-atos.html`, extraídos de lá em
vez de baixados de novo. Conferido antes da troca, com `font-synthesis: none`, que são
fontes **variáveis**: os pesos 400 e 700 rendem larguras diferentes, o que fonte estática
não faz. Ou seja, a aparência da página foi preservada — os pesos continuam reais, não
sintéticos.
