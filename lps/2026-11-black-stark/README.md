# Black Stark Strong · nov/2026

LP de queima de estoque (Black Friday) com equipamentos geração 5 à pronta entrega.

## Resumo

| Item | Valor |
|------|-------|
| Objetivo | Gerar pedidos de orçamento de equipamentos em queima de estoque |
| Público | Donos de academia (B2B) |
| Oferta | Até 50% OFF em 19 equipamentos geração 5, à vista no PIX, frete não incluso |
| Validade | Até 30/11/2026 ou enquanto durar o estoque |
| CTA | Monta a seleção → formulário → abre o WhatsApp comercial com a seleção pronta |
| WhatsApp | `5545999265525` (variável `WHATS` no `index.html`) |
| URL | https://starkstrong.com.br/campanha/black-26/ (canonical da página; o /black-26 redireciona para cá) |
| Plataforma | HTML estático (escopo `.bk` para embutir na plataforma do site) |
| Prévia | https://l9films.github.io/lps_stark_strong/ (GitHub Pages, atualiza a cada push no `main`) |
| Status | em revisão |

## Estrutura

- `index.html`: página completa (CSS e JS inline). Produtos, preços, descontos e unidades ficam no array `P` do script.
- `img/`: fotos dos produtos (nome = código do produto), `logo.png` e `favicon-48.png`. A pasta mantém o nome `img/` porque o HTML aponta para ela.
- Arquivo de origem: `LP_Black_Stark_site.zip` (fora do Git).

## Rastreamento

GTM `GTM-N8D9H6CS` (mesmo container do site). Eventos enviados ao `dataLayer`:

| Evento | Quando | Parâmetros |
|--------|--------|------------|
| `add_to_orcamento` | adiciona um produto à seleção | `produto`, `categoria: black-26`, `codigo` |
| `formulario_enviado` | envia o formulário | `form_id: black-26`, `origem`, `itens`, `valor`, `moeda`, UTMs |
| `orcamento_enviado` | envia o formulário | `origem`, `itens`, `valor`, `moeda`, UTMs |

UTMs (`utm_source`, `utm_medium`, `utm_campaign`, `utm_id`, `utm_term`) são guardadas em `localStorage` na chave `ss_utms` (last-touch, mesma chave do site).

## Pendências

- [ ] `copy.md` com os textos aprovados (quem aprovou e quando)
- [ ] Preços "de" e descontos conferidos com o comercial (lastro para o "até 50% OFF", CDC/CONAR)
- [ ] Unidades em estoque confirmadas (`SHOW_QTY = true` está marcado como "aguardando confirmação do estoque")
- [x] `og:image` corrigido: aponta para https://starkstrong.com.br/campanha/black-26/img/9003.jpg
- [ ] Formulário sem aviso de LGPD e pedindo e-mail como obrigatório (padrão: nome, academia, cidade, WhatsApp)
- [ ] Fontes usadas são Barlow e Lexend Exa; o padrão da marca é League Spartan (títulos) + Inter (texto)
- [ ] Há hex soltos no CSS (`#0c0c0c`, `#cfcbc3` etc.) fora das variáveis
- [ ] Imagens em JPG; padrão é WebP/AVIF
- [ ] Checklist da seção 5 do CLAUDE.md antes de publicar
