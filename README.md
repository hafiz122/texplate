# texplate

Three LaTeX templates for university coursework. Each folder contains a standalone, compilable sample and its own `macros.tex` file that you can copy and edit.

| Template | Use it for |
| --- | --- |
| `statistics-report` | An analysis report with methods, results, a table, a figure placeholder, and conclusions |
| `problem-set` | Numbered questions with worked solutions |
| `assignment` | A general written assignment with a thesis, discussion, and references |

## Get started

Install a LaTeX distribution that includes `pdflatex` and `latexmk`, such as TeX Live or MacTeX. On Overleaf, upload the folder you want to use, set `main.tex` as the main document, and select pdfLaTeX.

Copy one template folder for your assignment. Replace the bracketed fields in `macros.tex`, then replace sample text and illustrative values in `main.tex` with your own work. To compile locally, run this from the copied folder:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -file-line-error -outdir=build main.tex
```

The PDF will be at `build/main.pdf`. Run the same command after edits; `latexmk` handles the necessary LaTeX passes. The `build` directory and common LaTeX auxiliary files are ignored by Git.

## Customize a template

- Edit the title, name, course, institution, and date near the top of `macros.tex`.
- Keep or remove example sections to match your instructor's requirements.
- Use `\SampleMean{x}`, `\Prob{A}`, `\Expect{X}`, and `\Variance{X}` in math mode in the statistics and problem set templates. The problem set also provides `\problem{Title}` and a `solution` environment.
- For a real figure, replace the statistics report's boxed placeholder with `\includegraphics[width=...]{your-file}` and put the image beside `main.tex` (or update the path).
- Replace the reference placeholder with the citation format required by your course. The samples do not claim to cite real sources.

The templates use standard packages available in common TeX Live installations. They do not require shell escape, external assets, or a custom document class.

## License

MIT. See [LICENSE](LICENSE).
