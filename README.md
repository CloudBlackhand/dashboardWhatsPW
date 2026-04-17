# WhatsPW — Dashboard (deploy estático)

## Dois repositórios

| Repo | Função |
|------|--------|
| **[dashboardWhatsPW-vite](https://github.com/CloudBlackhand/dashboardWhatsPW-vite)** | Código fonte: Vite + React + TanStack Table. **É aqui que desenvolves.** |
| **Este repo** (`dashboardWhatsPW`) | Artefacto servido pelo WAHA: `index.html`, `assets/`, … na **raiz** (gerado pela Action). |

## Publicar alterações do UI

1. Push em **[dashboardWhatsPW-vite](https://github.com/CloudBlackhand/dashboardWhatsPW-vite)** (`main`).
2. Neste repo, em **Actions** → **Publish dashboard build** → **Run workflow** (execução manual).
3. Atualiza `waha.config.json` → `dashboard.ref` no [WhatsPW](https://github.com/CloudBlackhand/WhatsPW) para o **último commit** da `main` deste repo (o commit da Action, se houver mudança).
4. Rebuild / redeploy da imagem WAHA.

## Referência Nuxt (WAHA original)

O bundle antigo do upstream está em [devlikeapro/dashboard](https://github.com/devlikeapro/dashboard) — usa-o só como referência de API/UX no teu clone local (`dashboard/`).
