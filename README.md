# DropZero — Radar de Jogos Grátis

PWA em português para encontrar ofertas temporárias de jogos da Steam, Epic Games Store e GOG.

## Recursos
- Layout responsivo para Windows e celular.
- Filtros por loja e pesquisa por título.
- Capas, prazo quando informado, valor original quando disponível e links para a loja.
- Destaque heurístico para jogos conhecidos/populares.
- Cache dos arquivos da interface e das últimas ofertas.
- Solicitação de notificações locais no navegador.

## Fonte dos dados
As ofertas vêm da API pública de terceiros GamerPower: https://www.gamerpower.com/api/giveaways. A API pode ficar indisponível, aplicar limites, ou não listar todas as promoções. O app não inventa avaliações: notas reais e idiomas estruturados não são consistentes para todas as lojas. A contagem de usuários/resgates é apenas um sinal de popularidade.

Os botões abrem uma pesquisa na loja correspondente; confirme preço, idioma, prazo e elegibilidade na página oficial antes de resgatar. Prazos e valores dependem da fonte e podem estar ausentes/desatualizados.

## Executar localmente
Com Python instalado, abra o terminal nesta pasta e execute:
```bash
python -m http.server 8080
```
Abra http://localhost:8080. O service worker e a instalação PWA funcionam em HTTPS ou localhost.

## Publicar no GitHub Pages
1. Abra Settings → Pages neste repositório.
2. Em Build and deployment, selecione Deploy from a branch.
3. Escolha a branch main e a pasta /(root), depois Save.
4. Aguarde a URL HTTPS aparecer na página do Pages.

## Instalar
- Windows: abra o site HTTPS no Chrome/Edge e escolha Instalar este site como aplicativo.
- Android: abra no Chrome e selecione Instalar app ou Adicionar à tela inicial.

## Limitações
Notificações desta versão são verificações locais enquanto o app está aberto; o navegador pode suspender tarefas em segundo plano. Push real com o app fechado requer backend e serviço push (Web Push/FCM), assinatura e configuração HTTPS. A priorização de português é apenas indicativa, baseada em texto encontrado na descrição, não uma confirmação de idioma.
