# docx2pdf

[![PyPI](https://img.shields.io/pypi/v/docx2pdfwlower)](https://pypi.org/project/docx2pdfwlower/)

Convert `docx` to `pdf` on Windows or macOS directly using Microsoft Word (**must be installed**).

On Windows, this is implemented via [`win32com`](https://pypi.org/project/pywin32/) while on macOS this is implemented via [JXA](https://github.com/JXA-Cookbook/JXA-Cookbook) (Javascript for Automation, aka AppleScript in JS).

## Install

Via [pipx](https://pipxproject.github.io/pipx/):

```
pipx install docx2pdfwlower
```

Via pip:

```
pip install docx2pdfwlower
```

## CLI

```
usage: docx2pdfwlower [-h] [--keep-active] [--version] input [output]

Example Usage:

Convert single docx file in-place from myfile.docx to myfile.pdf:
    docx2pdfwlower myfile.docx

Batch convert docx folder in-place. Output PDFs will go in the same folder:
    docx2pdfwlower myfolder/

Convert single docx file with explicit output filepath:
    docx2pdfwlower input.docx output.pdf

Convert single docx file and output to a different explicit folder:
    docx2pdfwlower input.docx output_dir/

Batch convert docx folder. Output PDFs will go to a different explicit folder:
    docx2pdfwlower input_dir/ output_dir/

positional arguments:
  input          input file or folder. batch converts entire folder or convert
                 single file
  output         output file or folder

optional arguments:
  -h, --help     show this help message and exit
  --keep-active  prevent closing word after conversion
  --version      display version and exit
```

## Library

```python
from docx2pdfwlowers import convert

convert("input.docx")
convert("input.docx", "output.pdf")
convert("my_docx_folder/")
```

See CLI docs above (or in `docx2pdfwlower --help`) for all the different invocations. It is the same for the CLI and python library.

## Jupyter Notebook

If you are using this in the context of jupyter notebook, you will need `ipywidgets` for the tqdm progress bar to render properly.

```
pip install ipywidgets
jupyter nbextension enable --py widgetsnbextension
``
