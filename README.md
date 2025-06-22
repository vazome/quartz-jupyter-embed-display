# Quartz Jupyter Notebook Embed Plugin

This package provides a Quartz-compatible plugin to embed and display Jupyter notebooks (.ipynb) in your Quartz-based site.

You can check it here: https://vazome.tech/AI-and-MLOps/MLOps-Theory

| Code | Images |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/f63fae48-74ba-4a35-b239-ce70d5034fcf" alt="Before styling" width="450"> | <img src="https://github.com/user-attachments/assets/acd9049a-4e0e-4f0f-ac02-88197de545db" alt="After styling" width="450"> |

## Installation

1. Copy `notebook.ts`**: Put it at `quartz\plugins\transformers\`
2. This plugin relies on `rehype-stringify` package, family of which is included by default in [@jackyzha0/quartz](https://github.com/jackyzha0/quartz), except this plugin... let's fix that:
```bash
npm install rehype-stringify
```
3. Append `Plugin.NotebookEmbedding` block **above** existing `SyntaxHighlighting` block in `quartz.config.ts`:
```typescript
      Plugin.NotebookEmbedding({
        cacheDir: "quartz/.quartz-cache/notebooks",
        downloadFromGitHub: true,
        downloadTimeout: 15000,
      }),
```
4. Append `export { NotebookEmbedding } from "./notebook"` to the end of the `quartz\plugins\transformers\index.ts`

##  Usage
- By default, this will embed any Jupyter notebook link `[notebook-name](URL)` ending in `.ipynb` as an interactive HTML widget in your site.
- Use markdown links in your notes to any public `.ipynb` file (on GitHub or elsewhere). The plugin will cache notebooks in `quartz/.quartz-cache/notebooks` by default.






























