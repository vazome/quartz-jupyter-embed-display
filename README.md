# Quartz Jupyter Notebook Embed Plugin

This package provides a Quartz-compatible plugin to embed and display Jupyter notebooks (.ipynb) in your Quartz-based site.

## Installation

1. **Copy `notebook.ts`**: Ensure `notebook.ts` is present in your Quartz plugin directory, or import it into your build step as needed.

2. **Install Required Packages**
This plugin relies on the following packages, which are NOT included by default in @jackyzha0/quartz:

- `fs/promises` (built-in Node.js >=v14)
- `unist-util-visit`
- `unified`
- `remark-parse`
- `remark-breaks`
- `remark-frontmatter`
- `remark-gfm`
- `remark-math`
- `remark-rehype`
- `remark-smartypants`
- `rehype-stringify`
- `hast-util-from-html`

Install with:
```bash
npm install unist-util-visit unified remark-parse remark-breaks remark-frontmatter remark-gfm remark-math remark-rehype remark-smartypants rehype-stringify hast-util-from-html
```

3. **Enable the Plugin**

- Import and configure the plugin in your Quartz build pipeline (see your Quartz plugin documentation for how to add a custom transformer plugin).
- By default, this will embed any Jupyter notebook link ending in `.ipynb` as an interactive HTML widget in your site.

4. **Usage**

- Use markdown links in your notes to any public `.ipynb` file (on GitHub or elsewhere). The plugin will fetch, cache, and display the notebook contents.

## Notes
- This plugin is designed for Quartz v4+.
- The plugin will cache notebooks in `quartz/.quartz-cache/notebooks` by default.
- To configure options (like disabling automatic download), edit the exported `NotebookEmbedding` options.
