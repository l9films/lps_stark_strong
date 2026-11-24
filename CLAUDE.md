# Stark Strong — Landing Pages

Repositório central das landing pages (LPs) da **Stark Strong**, fabricante brasileira de equipamentos de musculação para academias. Aqui ficam o código, os textos, os assets e o histórico de decisões de cada LP.

- Repositório: https://github.com/l9films/lps_stark_strong (branch principal: `main`)
- Produção: L9 Films
- Assinatura da marca: **"Menos promessa. Mais performance."**

> Este arquivo é a fonte de verdade do projeto. Quando uma decisão for tomada (nova LP, texto aprovado, número validado, pendência resolvida), atualize a seção correspondente aqui no mesmo commit.

---

## 1. Estrutura do repositório

```
lps_stark_strong/
├── CLAUDE.md              ← este arquivo (regras + índice de LPs)
├── index.html             ← página inicial: redireciona para a LP ativa (hoje lps/2026-11-black-stark/)
├── brand/                 ← logos, fontes, paleta, brandbook (PDF) e referências
├── shared/                ← CSS/JS/componentes reutilizados entre LPs
└── lps/
    └── <aaaa-mm>-<slug>/  ← uma pasta por LP (ex.: 2026-08-glute-strong-fitness-brasil)
        ├── README.md      ← briefing, objetivo, público, CTA, status, pendências
        ├── copy.md        ← textos aprovados (fonte da verdade do texto)
        ├── index.html     ← página (ou export/código da plataforma)
        └── assets/        ← imagens, renders e vídeos desta LP
```

Regras:
- Uma pasta por LP, nome em minúsculas com hífen, prefixado com ano-mês de lançamento.
- Todo texto aprovado vive em `copy.md` antes de ir para a página. Se o texto da página e o `copy.md` divergirem, vale o `copy.md`.
- Assets pesados (vídeo bruto, PSD, RAW) **não** entram no Git. Fica só o arquivo final otimizado (WebP/AVIF/MP4 comprimido); os originais ficam no Drive e o link vai no README da LP.
- Nunca commitar tokens, senhas, IDs de pixel privados ou credenciais da GreatPages/Meta. Use `.env` (ignorado pelo Git).

---

## 2. Índice de landing pages

Atualize esta tabela a cada LP criada, publicada ou encerrada.

| LP | Pasta | Plataforma | Objetivo / CTA | Status | URL |
|----|-------|------------|----------------|--------|-----|
| Glute Strong · Fitness Brasil Expo 2026 | `lps/2026-08-glute-strong-fitness-brasil` | GreatPages | Reserva de atendimento prioritário no stand F13 (Rua 1, 100 m²) · simulador de área | a confirmar (feira já ocorreu: 27–29/08/2026) | a preencher |
| Black Stark Strong · Black Friday 2026 | `lps/2026-11-black-stark` | HTML estático | Queima de estoque geração 5 (até 50% OFF, PIX) · seleção de equipamentos → WhatsApp comercial | em revisão | https://starkstrong.com.br/black-26/ (prevista) |

Status possíveis: `briefing` → `em produção` → `em revisão` → `publicada` → `encerrada`.

---

## 3. Marca — travas que valem para TODA LP

### Paleta
| Token | Hex | Uso |
|-------|-----|-----|
| preto | `#111111` | fundo dominante |
| grafite | `#1F2021` | texto sobre fundo claro |
| off-white | `#F3F1EC` | fundo claro |
| branco | `#FFFFFF` | texto sobre fundo escuro |
| ouro | `#C7A56A` | destaque: pouco, preciso, recorrente |

- **Vermelho não existe** em lugar nenhum da Stark, nem na Glute Strong.
- **Verde não faz parte da paleta** (inclusive botões; o botão de WhatsApp usa a paleta da marca, não o verde do app).
- O dourado **nunca ocupa grandes áreas**. Fica só em palavra-chave, linha fina, detalhe.

### Tipografia
- Títulos: **Arian LT**. Enquanto o arquivo da fonte não estiver em `brand/`, use **League Spartan** (Google Fonts) como substituta geométrica.
- Texto corrido: **Inter**.
- Legendas de vídeo (Reels embutidos): Montserrat Bold.
- Títulos em caixa alta com tracking aberto; dourado só na palavra de destaque.

### Logo
- Área de proteção = módulo "S" do logo. Nada invade.

### Linguagem
- Nunca a palavra **"sala"**. Sempre **"academia"**.
- **Angela Borges**, sem circunflexo. Sempre.
- Angela aparece em **terceira pessoa** nos textos institucionais; ela fala direto com o leitor apenas em vídeos de ads.
- Angela é **atleta e professora**, nunca "modelo". Sem sensualização.
- Posicionar pelos padrões da própria Stark/Angela, **nunca comparando com concorrentes**.
- **Superlativos e claims absolutos exigem lastro factual** (risco CONAR e CDC). Na dúvida, troque por especificação técnica.
- Reclame Aqui só entra como prova social depois de confirmar que o perfil está sob o nome "Stark Strong".

### Vocabulário técnico aprovado
Guias em inox AISI 304, solda estrutural, parede de tubo reforçada, Corvim sobre espuma de alta densidade.

### Posicionamento
- Público primário das LPs: **donos de academia (B2B)**.
- As quatro perguntas que toda LP B2B deve responder: *cabe no meu espaço? quanto tempo pra entregar? vai quebrar? isso me faz reter aluno?*
- Diferenciais: método de projeto (briefing → estudo de espaço → layout → montagem → resultado) com arquiteta no time, o que faz da Stark parceira de projeto e não só fornecedora; e estoque pronto, contra 90–120 dias da concorrência.
- A Glute Strong se vende como **área premium dentro da academia**, nunca como máquina avulsa. Tagline: *"GLUTE STRONG. A nova engenharia dos glúteos."*
- CTAs levam ao **WhatsApp comercial**.
- **Se o estoque acabar, retirar imediatamente qualquer menção a pronta entrega.**

---

## 4. Padrões técnicos das LPs

- Mobile first: a maior parte do tráfego vem de Instagram/ads. Testar em 375 px de largura antes de qualquer entrega.
- Peso: imagens em WebP/AVIF, lazy-load abaixo da dobra, LCP < 2,5 s.
- Cores como variáveis CSS (`--preto`, `--ouro` etc.), sem hex solto no código.
- Todo CTA com rastreamento (UTM + evento de pixel). Documentar os eventos no README da LP.
- Formulários: pedir só o necessário (nome, academia, cidade, WhatsApp) e ter aviso de LGPD.
- Simuladores ou cálculos (ex.: m² por estação, taxa de ocupação, ganho estimado) **só vão ao ar com coeficientes validados pela arquiteta**. Enquanto forem estimativa, marque na página como estimativa ou não publique.

---

## 5. Fluxo de trabalho

1. **Briefing:** criar `lps/<aaaa-mm>-<slug>/README.md` com objetivo, público, CTA, prazo, canais de tráfego e pendências. Adicionar a linha no índice (seção 2).
2. **Copy:** escrever em `copy.md`, revisar contra as travas da seção 3 e registrar quem aprovou e quando.
3. **Página:** construir/exportar. Commit por etapa, mensagem em português no imperativo (ex.: `Adiciona seção do método na LP Glute Strong`).
4. **Revisão:** checklist abaixo.
5. **Publicação:** registrar URL e data no índice. Mudar status para `publicada`.
6. **Encerramento:** ao fim da campanha, status `encerrada` + resultado (leads, conversão) no README da LP.

### Checklist antes de publicar
- [ ] Nenhum vermelho/verde; dourado só em detalhes
- [ ] Nenhuma "sala"; "Angela" sem acento
- [ ] Nenhum claim absoluto sem lastro
- [ ] Nenhuma comparação com concorrente
- [ ] Números do simulador validados pela arquiteta
- [ ] Prazo/estoque conferido com o comercial
- [ ] CTAs apontando para o WhatsApp correto, com UTM
- [ ] Testado em celular (iOS e Android) e desktop
- [ ] Pixel/eventos disparando

---

## 6. Pessoas e papéis

| Pessoa | Papel |
|--------|-------|
| Angela Borges | assina a linha Glute Strong; atleta e professora |
| Arquiteta (nome a preencher) | valida layouts e coeficientes de simuladores |
| Daiane Varasquin, Johann, Tenente Breno, treinador Antônio | presença no stand / conteúdo |
| L9 Films | produção de conteúdo e LPs |

---

## 7. Pendências em aberto

Herdadas do plano da Fitness Brasil (ago/2026). Confirmar se ainda valem e remover as resolvidas.

- [ ] Coeficientes do simulador da LP (fatores de ganho, m² por estação, taxa de ocupação de pico) validados pela arquiteta?
- [ ] Arquivo da fonte Arian LT, para colocar em `brand/fonts/`
- [ ] Perfil do Reclame Aqui está sob "Stark Strong" (não sob nome legado)?
- [ ] URL e plataforma definitivas da LP da Glute Strong, e se ela continua no ar depois da feira
- [ ] Brandbook completo (PDF) em `brand/`

---

## 8. Instruções para o Claude

- Responda e escreva em **português do Brasil**.
- Antes de escrever qualquer texto de LP, releia a seção 3. Se um pedido violar uma trava, avise e proponha alternativa em vez de executar.
- Não invente números, prazos, preços ou especificações. Se faltar dado, deixe `[A CONFIRMAR]` no texto e adicione a pendência na seção 7.
- Ao criar ou alterar uma LP, atualize o índice (seção 2) e o README da LP no mesmo commit.
- Não fazer push nem publicar nada sem pedido explícito.
