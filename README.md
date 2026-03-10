# Competitive Programming Notebook Generator

This script generates a **LaTeX competitive programming notebook** from the `code/` directory and compiles it into a PDF.

## Folder Rules

* Each **folder** inside `code/` becomes a **section**.
* Each **file** becomes a **subsection**.
* Use numeric prefixes to control ordering.

Example:

```
code/
 ├── 01-graph/
 │    ├── 01-dsu.cpp
 │    └── 02-dijkstra.cpp
 └── 02-dp/
      └── 01-knapsack.cpp
```

The prefix (`01-`, `02-`, etc.) is **only for ordering** and is removed in the final notebook.

## Supported Files

Code:

* `.cpp`, `.c`, `.cc`
* `.py`
* `.java`

Other:

* `.png`, `.jpg`, `.jpeg`, `.pdf` → inserted as images
* `.tex` → inserted directly as LaTeX content

Code files are included using **minted** for syntax highlighting.

## Usage

Run:

```
python3 script.py
```

This will:

1. Generate `contents.tex`
2. Compile `notebook.tex` into a PDF using `latexmk`.

## Requirements

* Python 3
* `latexmk`
* LaTeX with `minted`
* `pygments`
