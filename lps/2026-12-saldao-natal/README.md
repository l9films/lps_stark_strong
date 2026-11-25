# Saldão de Natal Stark Strong · dez/2026

Prévia de layout da LP de queima de estoque de Natal. Mesma mecânica da [Black Stark](../2026-11-black-stark/): catálogo com filtro por desconto → seleção → orçamento pelo WhatsApp.

## Resumo

| Item | Valor |
|------|-------|
| Objetivo | Gerar pedidos de orçamento de equipamentos em queima de estoque |
| Público | Donos de academia (B2B) |
| Oferta | Até 50% OFF em produtos selecionados, à pronta entrega, à vista no PIX, frete não incluso |
| Validade | 07/12 a 26/12/2026 ou enquanto durar o estoque (contagem regressiva na página) |
| CTA | Seleção → formulário → WhatsApp comercial (**ainda não ligado**) |
| Prévia | https://l9films.github.io/lps_stark_strong/lps/2026-12-saldao-natal/ |
| Plataforma | HTML estático, arquivo único (CSS/JS inline, árvore e pisca-pisca desenhados em SVG/canvas) |
| Status | em produção |

## Rastreamento

| Evento | Quando | Parâmetros |
|--------|--------|------------|
| `add_to_orcamento` | adiciona um produto | `produto`, `categoria: natal-26`, `codigo` |

Ainda sem GTM, sem captura de UTM e sem eventos de envio do formulário (a Black tem os três).

## Pendências

- [x] Produtos reais da Black (19 itens: nomes, fotos, preços, descontos) — fotos lidas de `../2026-11-black-stark/img/`
- [ ] Atualizar o estoque por produto (hoje ainda é o da Black)
- [ ] Estoque por produto confirmado com o comercial (a página mostra "Só X unidades")
- [ ] Ligar o envio do formulário ao WhatsApp comercial (hoje o botão só mostra "Prévia: aqui abre o WhatsApp")
- [ ] Adicionar GTM `GTM-N8D9H6CS`, UTMs (`ss_utms`) e eventos `formulario_enviado` / `orcamento_enviado`
- [ ] Logo em imagem (hoje é texto) e favicon próprio
- [ ] Aviso de LGPD no formulário; e-mail está obrigatório (padrão: nome, academia, cidade, WhatsApp)
- [ ] Remover o selo "Prévia · natal-26" e o aviso de dados de exemplo
- [ ] Remover o `noindex` quando os dados forem reais; adicionar canonical e Open Graph
- [ ] `copy.md` com textos aprovados
- [ ] Checklist da seção 5 do CLAUDE.md
