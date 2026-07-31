# Combo PND 2026 — landing page

Página de vendas estática (HTML + CSS + JS puro, sem build) para o Combo PND 2026:
4 materiais da Formação Geral Docente da Prova Nacional Docente (20/09/2026).

## Estrutura

```
index.html      página completa
img/            previews das páginas dos PDFs
vercel.json     headers de cache + configuração de deploy estático
```

## Colocar o link do Hotmart

Abra `index.html`, procure por `CHECKOUT_URL` (perto do fim do arquivo) e cole a URL do checkout:

```js
var CHECKOUT_URL = "https://pay.hotmart.com/SEU-CODIGO";
```

Todos os botões de compra passam a apontar para lá automaticamente.
Enquanto a variável estiver vazia, os botões apenas rolam até a seção de oferta.

## Rodar localmente

```bash
python -m http.server 8000
# abra http://localhost:8000
```

## Deploy

Deploy estático — sem framework, sem build step. Na Vercel, importar o repositório
e deixar Framework Preset em **Other**; Build Command e Output Directory ficam vazios.

## Antes de publicar

- [ ] Colar a `CHECKOUT_URL` do Hotmart
- [ ] Conferir se a garantia de 7 dias corresponde à configurada no Hotmart
- [ ] Remover o bloco de escassez (`.stock`) se não houver lote limitado real
- [ ] Trocar o preço em todos os lugares caso mude a promoção (busque por `7,90`)
