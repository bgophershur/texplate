# 📘 Physics Lab Report Template (Hebrew + XeLaTeX)

This is a modular LaTeX template for physics lab reports, designed for RTL Hebrew text, mathematical equations, uncertainty analysis, and a clean academic structure.

Includes:
- RTL Hebrew support via `polyglossia` + `fontspec`
- Modular document structure (`main.tex`, `sections/`, `commands.tex`, etc.)
- Custom variables for lab/course info
- Ready-to-print PDF formatting
- Preconfigured preamble for fonts, packages, and style

---

## 🦌 How to Use
For cover, edit variables in `variables.tex`
Then just edit each page. Feel free to edit the configuration as you wish!

## 🚀 How to Compile

You have multiple options:

---

### 💻 Option 1: **Local (TeX Live + VS Code)**

#### 🔧 Requirements
- [TeX Live](https://www.tug.org/texlive/) (or MiKTeX on Windows)
- [Visual Studio Code](https://code.visualstudio.com/)
- [LaTeX Workshop extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)

#### 📂 Directory Setup
Make sure this is your structure:

```
lab-report/
│
├── main.tex
├── preamble.tex
├── commands.tex
├── sections/
│   ├── titlepage.tex
│   ├── ...
└── images/
```

#### ▶️ Compile with XeLaTeX:
In VS Code, open the Command Palette and run:
```
LaTeX Workshop: Build with recipe → XeLaTeX
```

Or add to `.vscode/settings.json`:
```json
{
  "latex-workshop.latex.recipe.default": "lastUsed",
  "latex-workshop.latex.recipes": [
    {
      "name": "XeLaTeX",
      "tools": ["xelatex"]
    }
  ],
  "latex-workshop.latex.tools": [
    {
      "name": "xelatex",
      "command": "xelatex",
      "args": ["-synctex=1", "-interaction=nonstopmode", "-file-line-error", "%DOC%"]
    }
  ]
}
```

---

### 🌐 Option 2: **Overleaf (Online)**

1. Go to [Overleaf](https://www.overleaf.com/)
2. Create a new project → Upload all files (`main.tex`, `preamble.tex`, etc.)
3. Set **compiler to XeLaTeX** in the Overleaf menu
4. Hit **Recompile**

Overleaf will handle the font setup and RTL rendering automatically.

---

### 🐧 Option 3: **Command-line (Linux/macOS)**

```bash
cd lab-report
xelatex main.tex
```

If you want to compile everything in one shot (twice for TOC):

```bash
xelatex main.tex && xelatex main.tex
```

---

## 🧼 Clean Output (Optional)

To ignore unnecessary build files in Git:
```bash
cp .gitignore-template .gitignore
```

---

## 🧠 Author Info

- Written by: **Opher Shur**
- Language: Hebrew 🇮🇱 + English 🇬🇧
- Engine: XeLaTeX via `fontspec`, `polyglossia`, `bidi`

---

## 📄 License

Free to use, remix, and publish academic reports.  
Just don’t submit as your own work if you’re not named Opher 😉
