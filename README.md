# Apuração 2026 (Presidente + Governador)

Site estático: um único `index.html`. Lê direto os JSON públicos do TSE no navegador.

## Publicar no GitHub Pages
1. Crie um repositório e envie estes arquivos (incluindo `.nojekyll`).
2. Settings → Pages → Deploy from a branch → `main` / root.
3. Abra `https://SEU-USUARIO.github.io/SEU-REPO/`.

Para ver o layout sem dados reais: `.../?demo`.

## Configuração (topo do `<script>`)
- `GOV_UFS`: estados/DF com 2º turno para governador (hoje AC, AM, DF, ES, RJ, RN, TO).
- `ELEICOES`: códigos do TSE (1º turno 6257/6259, 2º turno 6258/6260).
- Cores: `--lula` (vermelho) e `--bolso` (azul) no CSS. A cor é decidida pelo nome do candidato (contém "Lula" ou "Bolsonaro").

## Se aparecer erro de leitura do TSE (CORS)
Ative o workflow `.github/workflows/espelho.yml`: ele copia os arquivos para `dados/` a cada ~5 min
e a página passa a ler de lá automaticamente (atualização mais lenta).
