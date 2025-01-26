# LaTeX Template

本專案提供了一個簡潔的 LaTeX 範本，旨在協助使用者快速開始撰寫高品質的文件。該範本支援程式碼語法高亮顯示，並使用 `minted` 套件進行程式碼的格式化展示。

## 目錄結構

```
latex-template/
├── images/             # 圖片資源目錄
├── .gitignore          # Git 忽略清單
├── README.md           # 專案說明文件
├── main.pdf            # 編譯後的 PDF 文件
├── main.tex            # 主 LaTeX 文件
└── makefile            # 自動化編譯腳本
```

## 系統需求

- **Python**：請確保系統已安裝 Python，建議使用最新版本。
- **Pygments**：需要安裝 Pygments 套件以支援程式碼語法高亮。安裝方法如下：
  ```bash
  pip install Pygments
  ```
- **TeX Live**：建議安裝 [TeX Live](https://www.tug.org/texlive/)，這是一個跨平台的 TeX 發行版，包含了大部分常用的 TeX 套件和工具。
- **XeLaTeX**：請確保您的 TeX 發行版中包含 XeLaTeX。對於基於 Debian 的系統，可以使用以下命令安裝：
  ```bash
  sudo apt-get install texlive-xetex
  ```

## 使用方法

1. **複製儲存庫**

   ```bash
   git clone https://github.com/AaronWu-train/latex-template.git
   cd latex-template
   ```

2. **編譯文件**

   您可以使用 `makefile` 來自動化編譯過程。請確保您的系統已安裝 `make` 工具，然後執行：

   ```bash
   make
   ```

   這將執行以下命令來編譯 `main.tex`：

   ```bash
   xelatex -shell-escape main.tex
   bibtex main
   xelatex -shell-escape main.tex
   xelatex -shell-escape main.tex
   ```

   **注意**：使用 `minted` 套件進行程式碼高亮時，需要啟用 `-shell-escape` 選項，以允許 LaTeX 在編譯過程中調用外部程式（如 `pygmentize`）。

3. **自訂內容**

   - **主文件**：在 `main.tex` 中撰寫您的內容。
   - **圖片**：將所需圖片放置於 `images/` 目錄，並在 `main.tex` 中引用。

## 貢獻

歡迎對本專案提出建議、報告問題或提交改進。您可以透過 GitHub 的 Issues 或 Pull Requests 功能與我們交流。

## 授權

本專案採用 MIT 授權條款。詳情請參閱 [LICENSE](./LICENSE) 文件。
