# Palpiteiro's Big Burguer — site 2026

Site estático de duas páginas. Sem build, sem dependências: abra `index.html`.

```bash
cd ~/Documents/palpiteiros-site && python3 -m http.server 4180
```

A estrutura segue o site da Old Man Sandwich Shop (`~/Documents/oldman-site`):
página única com hero, faixa rolante, como pedir, destaque, vitrine de lanches,
casas, Instagram, FAQ, dock no celular e um `cardapio.html` separado em folha de
papel. A identidade é da Palpiteiro's.

## Estrutura
- `index.html` — a home inteira (CSS e JS embutidos)
- `cardapio.html` — cardápio completo: 13 lanches, 15 combos, 8 porções e bebidas
- `assets/img/menu/` — fotos dos produtos, do app de pedidos (512 px)
- `assets/img/ig/` — miniaturas dos posts, nomeadas `NN-<id do post>.jpg`
- `assets/img/logo-selo.png` — o selo recortado em círculo; `logo-tile.png` é o favicon
- `assets/img/logo-src-gplus.jpg` — o selo original, como veio do app (256 px)

## Cores: saíram da marca
- `--ink #0B0A09` — o preto do selo
- `--orange #F8931F` — a borda laranja do selo, medida no pixel. Virou a cor de ação
- `--paper #E6D5B8` e `--kraft #B08A5E` — o saco kraft de entrega que aparece em quase toda foto

Títulos em Roboto Slab, porque o letreiro do selo e do saco é uma slab grossa.
A diferença da Old Man (preto com dourado, Oswald) é proposital: o esqueleto é o
mesmo, a cara é outra.

## De onde vieram os dados (07/10/2026)

| Dado | Fonte |
|---|---|
| Telefone/WhatsApp (11) 93097-4774 e horário | Bio do Instagram @palpiteirosbigburguer |
| Cardápio completo com preços | App de pedidos (app.gplustogo.com.br/palpiteirosburger) |
| Formas de pagamento, delivery ~45 min, retirada 0–10 min | Mesmo app |
| Endereço Jd Paraguaçu, CEP, faixa R$ 20–40 | Google Maps |
| Endereço São Mateus e @palpiteirosbigburguersm | Google Maps e grid do Instagram |
| "O melhor do artesanal" | Texto de reel da própria casa (jul/2026) |
| Foto do hero e fachada de São Mateus (placa "1098") | Fotos públicas do Google Maps |
| As três frases de cliente | Destaques de avaliação do Google, unidade São Mateus (5,0 com 9 notas) |

## Conferir com a operação antes de publicar

1. **Segunda-feira.** A bio do Instagram diz terça a domingo; o app de pedidos
   lista segunda das 18h às 23h. O site segue o Instagram (segunda fechada).
   **Confirmar qual vale.** A regra está em `H` no script do `index.html`.
2. **São Mateus não tem horário nem telefone públicos.** O site mostra só
   endereço e Instagram. Se o horário for o mesmo, dá pra repetir o bloco.
3. **O que vem no combo.** O app não diz. O site afirma "com fritas" porque o
   Combo Baby avisa que vem onion rings *no lugar das fritas*. Confirmar se tem
   bebida (os preços, +R$ 10 a 12, sugerem que não).
4. **O app de pedidos é de qual unidade?** O link da bio aponta para a loja com
   endereço do Jd Paraguaçu. Se São Mateus tiver loja própria no app, ela precisa
   de botão separado.
5. **Nota no Google.** A unidade Jd Paraguaçu tem 4,3 com 104 avaliações, e as
   mais recentes reclamam de pedido incompleto e atendimento. Por isso o site **não
   mostra nota** e a FAQ manda problema de pedido direto pro WhatsApp. Vale a
   operação olhar isso antes de puxar tráfego pro site.
6. **Keeta.** Um reel mostra o lanche na frente da marca Keeta. Se a casa estiver
   lá, dá pra adicionar como canal.
7. **Nome.** A marca escreve "Palpiteiro's" no selo e "Palpiteiros" no Instagram.
   O site usa "Palpiteiro's Big Burguer", que é o que está no selo.

## Faltam

- **Logo em vetor.** O maior selo público tem 256 px. No header (44 px) fica
  nítido; no hero (132 px) aguenta. Com o SVG ou PNG grande da operação, trocar
  `logo-selo.png`.
- **Fotos em alta.** Produtos estão em 512 px e posts em 640 px. O hero usa
  `hero-burger.jpg` (1284 px, do Google Maps da casa), que no desktop ocupa só
  a metade direita para não borrar. Com os originais da produção dá pra levar
  a foto pra tela inteira.
- **Vídeo.** A Old Man tem o reels do burger do mês rodando. Aqui não deu: o
  Instagram exige login para os vídeos. Se vier um reel em MP4, o bloco `.reel`
  e o `servidor.py` da Old Man servem do jeito que estão.
- **Domínio.** A casa não tem site; nenhum domínio foi encontrado.

## Atualizar

Preço e cardápio envelhecem. A fonte é o app de pedidos; a data da conferência
está no rodapé da folha em `cardapio.html`. Para trocar posts do Instagram, baixe
as novas miniaturas em `assets/img/ig/` e troque os blocos `<a class="ig-tile">`
(as URLs do CDN do Instagram expiram em cerca de um dia, por isso as imagens
ficam no repositório).
