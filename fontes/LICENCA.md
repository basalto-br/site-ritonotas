# Fontes servidas por este domínio

As três famílias são redistribuídas aqui em `.woff2`, subconjunto latino, em versão
variável — um arquivo por família cobre toda a faixa de peso.

| Arquivo | Família | Autoria | Licença | Origem |
|---|---|---|---|---|
| `inter.woff2` | Inter | Rasmus Andersson | SIL Open Font License 1.1 | extraída do `controle-atos.html` |
| `jetbrains-mono.woff2` | JetBrains Mono | JetBrains | SIL Open Font License 1.1 | extraída do `controle-atos.html` |
| `source-serif-4.woff2` | Source Serif 4 | Frank Grießhammer / Adobe | SIL Open Font License 1.1 | Google Fonts, subconjunto latino |

A SIL OFL 1.1 permite uso, estudo, modificação e redistribuição, inclusive comercial,
desde que os arquivos de fonte não sejam vendidos isoladamente e que o aviso de licença
acompanhe a redistribuição. É o que este arquivo faz.

Texto integral da licença: <https://openfontlicense.org>

## Por que estão aqui

Até 18/08/2026 a landing carregava estas fontes do Google Fonts. Cada visitante entregava
IP e User-Agent a um terceiro, sem escolha — incoerente numa página cujo argumento central
é que o dado do cartório não sai do lugar.

## Por que duas origens diferentes

**Inter e JetBrains Mono** saíram do próprio `controle-atos.html`, que já as embutia em
base64. Medido antes de trocar: rendem **pixel a pixel** o mesmo que o Google servia, em
parágrafos, listas, `h1` e `h3`.

**Source Serif 4 não pôde vir dali.** A cópia embutida no app é variável só de peso; a que
o Google entrega tem também o **eixo óptico** (`opsz`), que estreita o desenho nos tamanhos
grandes. Com a cópia do app, dois subtítulos passavam a quebrar em duas linhas e a página
ficava 78 px mais alta. Por isso esta veio direto do Google Fonts.

O eixo óptico é aplicado sozinho pelo navegador (`font-optical-sizing: auto` é o padrão).
Não mexer com `font-variation-settings`: fixar o `opsz` desfaz justamente o que se ganhou.

## Nota sobre o app

O `controle-atos.html` continua com a cópia sem eixo óptico embutida em base64. Não é
defeito lá — o app usa a serifada em poucos lugares e não tem o mesmo problema de quebra.
Mas se algum dia a tipografia do app for revista, é a mesma diferença que vai aparecer.
