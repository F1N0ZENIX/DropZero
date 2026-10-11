# DropZero

**Radar de jogos grátis para PC.** Encontre ofertas temporárias da Steam, Epic Games Store e GOG em uma interface rápida, em português e instalável no Windows ou celular.

[**Abrir o DropZero**](https://f1n0zenix.github.io/DropZero/) · [Código-fonte](https://github.com/F1N0ZENIX/DropZero)

![Ícone do DropZero](icon.svg)

## Recursos

- **Ofertas em um só lugar:** Steam, Epic Games Store e GOG.
- **Capas e informações:** prazo quando informado, valor original quando disponível e popularidade reportada.
- **Busca e filtros:** filtre por loja, procure pelo nome ou veja todos os resultados.
- **Marcação “Já coletado”:** marque jogos que já resgatou, desmarque quando quiser e filtre para ver apenas os marcados. A lista fica salva localmente neste navegador/dispositivo.
- **Atalho da Epic:** ofertas da Epic abrem a página oficial de jogos grátis: https://store.epicgames.com/free-games
- **PWA instalável:** interface responsiva, ícone próprio e cache básico para conexão instável.
- **Notificações locais:** o navegador pode avisar sobre novas ofertas enquanto o app está aberto e executando.

## Fonte dos dados e confiabilidade

As ofertas são consultadas na API pública de terceiros [GamerPower](https://www.gamerpower.com/api/giveaways). A disponibilidade, os prazos e os campos retornados dependem dessa fonte e podem mudar ou ficar temporariamente indisponíveis.

O DropZero usa sinais de popularidade e uma lista de títulos conhecidos para ordenar destaques. **Popularidade não é uma nota de avaliação.** A API não fornece avaliações consistentes para todas as lojas, então o app não inventa notas. A indicação de português é aproximada, baseada em texto encontrado na descrição. Confirme idioma, preço, prazo e condições diretamente na loja oficial.

Os links da Steam e da GOG levam a uma pesquisa na loja. Os links da Epic levam à página oficial de jogos grátis. Uma oferta pode terminar antes da próxima atualização.

## Executar no computador

É necessário ter Python instalado.

1. Baixe ou clone este repositório.
2. Abra o terminal dentro da pasta do projeto.
3. Execute:

   ```bash
   python -m http.server 8080
   ```

4. Abra http://localhost:8080 no navegador.

O service worker e os recursos PWA funcionam em **HTTPS** ou em `localhost`; abrir o arquivo HTML diretamente não ativa todos os recursos.

## Publicar com GitHub Pages

1. Abra **Settings → Pages** no repositório.
2. Em **Build and deployment**, selecione **Deploy from a branch**.
3. Escolha a branch `main` e a pasta `/(root)`.
4. Clique em **Save** e aguarde a publicação.
5. A URL esperada é https://f1n0zenix.github.io/DropZero/.

## Instalar como aplicativo

- **Windows (Chrome/Edge):** abra o site publicado em HTTPS e escolha **Instalar este site como aplicativo** no navegador.
- **Android (Chrome):** abra o site publicado, toque no menu e escolha **Instalar app** ou **Adicionar à tela inicial**.

## Limitações conhecidas

- O app depende de uma API externa e de conexão para atualizar ofertas.
- As notificações atuais são locais e não garantem alertas com o app fechado. Push confiável em segundo plano exige backend e Web Push/FCM.
- “Já coletado” é salvo no armazenamento local do navegador; não sincroniza entre dispositivos ou navegadores.
- Notas de avaliação e suporte a idiomas não são uniformes na fonte de dados.
- Verifique sempre os detalhes na página oficial antes de resgatar.

## Tecnologias

HTML, CSS e JavaScript sem framework; Web App Manifest; Service Worker; API GamerPower.