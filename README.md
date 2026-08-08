# Aurum Imobiliária — site institucional (demo)

Landing page de página única para imobiliária, construída como demonstração
comercial: mostra a donos de imobiliárias locais o que um site profissional
faz pela captação de clientes.

Todo o conteúdo visível está em português do Brasil. Código, comentários e
nomes de variáveis em inglês.

## Stack

Nenhuma. É um único `index.html` com CSS e JavaScript embutidos — sem build,
sem dependências, sem framework. Basta abrir o arquivo ou subir a pasta em
qualquer hospedagem estática.

As únicas requisições externas são as duas fontes do Google Fonts (Fraunces e
Inter), carregadas com `display=swap` e com pilha de fallback do sistema, de
modo que nada bloqueia a renderização.

## Estrutura

```
index.html      página completa (HTML + CSS + JS)
fotos/          11 imagens (Pexels — uso comercial livre, sem atribuição)
```

## Seções

Hero · barra de números · busca · 6 imóveis em destaque · diferenciais ·
como funciona · depoimentos · CTA para proprietários · regiões atendidas ·
FAQ · CTA final · rodapé.

## Conversão

Todos os CTAs apontam para o WhatsApp com mensagem pré-preenchida e
contextual — o botão de um imóvel específico já abre a conversa citando o
código, o bairro e o preço. O formulário de busca monta a mensagem a partir
dos filtros escolhidos em vez de fazer uma busca real.

## Personalização

1. **Número do WhatsApp** — altere `WHATSAPP_NUMBER` no `<script>` ao final do
   arquivo. O mesmo número está fixo em cada `href` como fallback para quando
   o JavaScript estiver desativado: um Localizar e Substituir de
   `5535999999999` atualiza os dois de uma vez.
2. **Textos da agência** — procure por `[EDIT]` no arquivo. Marca nome,
   CRECI, endereço, horários, números da barra de estatísticas e bairros.
3. **Fotos** — substitua os arquivos em `fotos/` mantendo os nomes.
   Imóveis 900x620, hero 800x1000, clientes 160x160.
4. **Mapa** — a seção "Regiões atendidas" tem um mapa ilustrado em SVG e um
   comentário indicando onde colar o embed do Google Maps.

## Acessibilidade e desempenho

- Imagens com `width`/`height` (evita salto de layout) e `loading="lazy"`,
  exceto o hero
- Acordeão do FAQ e menu mobile com `aria-expanded`; modal com foco
  gerenciado e fechamento por `Esc`
- `prefers-reduced-motion` desativa todas as animações
- Ícones em sprite SVG único, reaproveitado por `<use>`
