# WhatsPW — Dashboard

Recomenda-se clonar com um nome claro, **sem** chamar a pasta só `dashboard` (confunde com o bundle antigo):

`git clone https://github.com/CloudBlackhand/dashboardWhatsPW.git dashboardWhatsPW`

## Estrutura

- **`dashboard-new/`** — código fonte (Vite + React + TanStack Table). É aqui que se edita o painel.
- **Raiz do repo** (`index.html`, `assets/`, …) — saída **gerada automaticamente**; não editar à mão na `main`.

## Fluxo

1. Alteras ficheiros em `dashboard-new/`.
2. Fazes `git push` para `main`.
3. A GitHub Action **Publish dashboard build** corre `npm install` + `npm run build`, remove o bundle antigo (Nuxt) da raiz e copia o conteúdo de `dashboard-new/dist/` para a raiz, fazendo **commit + push**.

O WAHA lê este repositório pelo ZIP do commit em `waha.config.json` → `dashboard.ref`. Depois de cada publicação automática, atualiza o `ref` para o **último commit** da `main` (o da Action ou o teu, o que for mais recente).

## Desenvolvimento local

```bash
cd dashboard-new
npm install
npm run dev
```

Abre `http://localhost:5173/dashboard/` (com WAHA a correr; vê `dashboard-new/README.md`).
