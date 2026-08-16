# Site — Rito Notas

Landing page do produto de controle de protocolos de atos notariais.

Página única, estática, sem JavaScript e sem build. Publica na Cloudflare Pages.

## Rodar localmente

Abra o `index.html` direto no navegador. Não precisa de servidor.

Se preferir servir por HTTP:

```
python -m http.server 8000
```

## Publicar

Cloudflare Pages conectado a este repositório.

| Configuração | Valor |
|---|---|
| Framework preset | None |
| Build command | *(vazio)* |
| Build output directory | `/` |
| Domínio | `ritonotas.com.br` |

Cada push em `main` publica. Branches diferentes geram preview automático.

## Antes de publicar

- [ ] Abrir no celular, que é onde a maioria dos tabeliães vai ver
- [ ] Testar o link do WhatsApp no próprio celular
- [ ] Publicar a política de privacidade e repor os links no rodapé
- [ ] Conversa de autorização pendente — ver CLAUDE.md
- [x] ~~Captura `img/tela-lista.png`~~ — 1400×1395, dados fictícios
- [x] ~~Conferir a captura~~ — nenhum dado real de cliente
- [x] ~~Número do WhatsApp~~ — nas 3 ocorrências
- [x] ~~E-mail de contato~~ — `contato@ritonotas.com.br`
- [x] ~~Razão social e CNPJ~~ — linha removida até o CNPJ existir

## Estrutura

```
index.html      a página inteira
img/            capturas de tela
robots.txt
_headers        cabeçalhos de segurança (Cloudflare Pages)
CLAUDE.md       contexto para sessões de IA
```

Ver `CLAUDE.md` para decisões de marca, escopo do produto e restrições técnicas.
