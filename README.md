# Apuração 2026 (Presidente + Governador)

Site estático: um único `index.html`. Lê direto os JSON públicos do TSE no navegador.

## Publicar no GitHub Pages
1. Crie um repositório e envie estes arquivos (incluindo `.nojekyll`).
2. Settings → Pages → Deploy from a branch → `main` / root.
3. Abra `https://SEU-USUARIO.github.io/SEU-REPO/`.

Para ver o layout sem dados reais: `.../?demo`.

## Configuração (topo do `<script>`)
- `GOV_UFS`: estados/DF com 2º turno para governador (hoje AC, AM, DF, ES, RN, TO; o RJ foi decidido no 1º turno).
- `ELEICOES`: códigos do TSE (1º turno 6257/6259, 2º turno 6258/6260).
- Cores: `--lula` (vermelho) e `--bolso` (azul) no CSS. A cor é decidida pelo nome do candidato (contém "Lula" ou "Bolsonaro").

## Se aparecer erro de leitura do TSE (CORS)
Ative o workflow `.github/workflows/espelho.yml`: ele copia os arquivos para `dados/` a cada ~5 min
e a página passa a ler de lá automaticamente (atualização mais lenta).

## Rádio (música ambiente)
O botão "♪ Ligar rádio" toca uma música ambiente gerada no próprio navegador (sem direitos autorais).
Navegadores só liberam som depois de um clique, então alguém precisa apertar o botão.
Para tocar suas próprias músicas, coloque os arquivos numa pasta `musicas/` do repositório e liste em `MUSICAS`
no topo do bloco "RÁDIO" do `index.html`. Use só músicas que você tem direito de usar em um site público.

## Filtro por região e YouTube
- Os botões acima do mapa (Norte, Nordeste, Centro-Oeste, Sudeste, Sul) dão zoom na região e mostram o placar somado dela.
- O botão "YouTube" deixa qualquer visitante colar o link de um vídeo ou playlist para tocar no player do canto da tela.
  Para já abrir o site com uma playlist sua, coloque o link em `YOUTUBE` no bloco "RÁDIO" do `index.html`.

## Rádio com YouTube (rodízio)
A lista padrão está em `YOUTUBE_LISTA` (IDs dos vídeos) e o tempo em `MIN_POR_VIDEO` (15 minutos), no bloco "RÁDIO" do `index.html`.
A rádio toca ~15 minutos de cada vídeo, passa para o próximo e, no fim da lista, volta ao primeiro retomando de onde parou.
Se um vídeo não permitir incorporação, ele é pulado automaticamente.
