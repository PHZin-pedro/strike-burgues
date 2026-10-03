# Strike Burgue's — sistema do atendente

Versão renovada baseada no cardápio enviado.

## O que tem
- Cardápio mobile com visual preto/amarelo/vermelho inspirado no cardápio.
- Hambúrgueres, batatas, cachorro-quente, adicionais, bebida e Promoção Trio Bomba.
- Pedido rápido com quantidade e observação.
- Envio para cozinha e impressão ESC/POS por impressora de rede.
- Fallback de impressão pelo navegador.
- Estoque com +/-, edição, entrada de estoque e cadastro de novos itens.
- Produtos com cadastro/edição e ingredientes que baixam o estoque automaticamente.
- Histórico completo das vendas, busca, filtro por data e resumo de faturamento.
- Backup/exportação e importação JSON.
- Sem React, TypeScript, better-sqlite3 ou dependência de Python.

## Rodar no computador
```bash
npm install
npm start
```
Abra `http://localhost:3000`.

## Testar no celular
1. Computador e celular na mesma Wi-Fi.
2. No Windows, rode `ipconfig` e veja o IPv4 do computador.
3. No celular abra `http://IP-DO-COMPUTADOR:3000`.
4. Se o Windows perguntar sobre firewall, permita o Node na rede privada.

## GitHub Pages
O projeto também funciona como site estático. No GitHub Pages, os dados ficam no `localStorage` do navegador: fechar e abrir o mesmo link no mesmo aparelho mantém produtos, estoque e histórico.

**Importante:** GitHub Pages sozinho não possui banco de dados compartilhado. Para ter o MESMO estoque/histórico simultaneamente em vários celulares/computadores, será necessário conectar este frontend a um backend/banco online. O sistema já deixa o backup JSON pronto para isso.

## Impressora
Para impressão automática direta, use impressora térmica de rede (Wi-Fi/Ethernet) com ESC/POS e informe o IP/porta nas configurações. O servidor Node envia para a porta TCP (normalmente 9100).

Bluetooth/USB diretamente pelo celular normalmente precisa de uma ponte Android/nativa; navegador puro não garante esse acesso.

### Publicar no GitHub Pages
1. Crie um repositório no GitHub e envie todos os arquivos deste projeto para a branch `main`.
2. O workflow `.github/workflows/pages.yml` publica automaticamente a pasta `public`.
3. No GitHub, abra **Settings → Pages** e selecione **GitHub Actions** como fonte, se ainda não estiver selecionado.
4. Depois do primeiro workflow verde, abra o endereço do Pages.

O endereço do Pages funciona como cardápio/sistema do atendente e mantém os dados no navegador através do `localStorage`.
