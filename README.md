# Quartz Jupyter Notebook Embed Plugin
This package provides a Quartz-compatible plugin to embed and display Jupyter notebooks (.ipynb) in your Quartz-based site.

## Installation

1. Copy `notebook.ts`**: Put it at `quartz\plugins\transformers\`
2. Install Required Packages: This plugin relies on `rehype-stringify`, which is NOT included by default in @jackyzha0/quartz:
Install with:
```bash
npm install rehype-stringify
```
3. Append `Plugin.NotebookEmbedding` block **above** existing `SyntaxHighlighting` block
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


