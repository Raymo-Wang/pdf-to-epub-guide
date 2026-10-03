我最近找到了一本很好的电子书，但它是扫描版的pdf，无论在pad还是kindle上看都很不方便，没法调整字体，摘录文字等。于是我就研究了这一套从扫描pdf制作epub电子书的方法，亲测有效，也是美美的在Kindle中看上了，分享给和我有同样困惑的朋友们。

**第1步：原始pdf OCR成带文字层的pdf。**

这里我建议使用[ABBYY FineReader PDF](https://pdf.abbyy.com/)，它的OCR功能十分强大，可以在原始pdf相应位置覆盖文字层，有条件支持一下正版，没有条件可以看看闲鱼。

**第2步：将pdf转化为markdown文件。**

下载微软官方的[markitdown](https://github.com/microsoft/markitdown)工具，不仅免费而且功能强大，转换快速精确。

**第3步：md文件做格式清洗与ocr的文字校对。**

这一步其实是最繁琐的环节，但现在有codex，可以极大解放人力。这一步我建议让codex分两小步做，首先只做格式清洗，不校对正文；然后专门去做OCR文字校对，解决ocr识别的错误的文字。（可以让chatgpt生成两小步的提示词，再让codex执行）。

**第4步：使用Pandoc由[book.md, cover.jpg, epub.css]生成epub文件。**

[Pandoc](https://github.com/jgm/pandoc)工具可以在github上Pandoc官方的releases页面下载，下载对应系统的zip文件后解压，并把解压后的路径加入windows的PATH中。cover.jpg是封面图片，自己找个合适的图片另存为/保存即可。.css文件用于文本显示格式控制，.css文件里的代码段可以让codex帮忙填充。

**第5步：使用Sigil/EPUBCheck检查验证第4步生成的epub。**

[Sigil](https://github.com/Sigil-Ebook/Sigil)软件可以直接从 Sigil 官方 GitHub Releases 下载，在页面底部找到assets，选择windows x64安装程序；下载完成后使用Sigil打开epub，检查一下封面，章节，正文排版，标题层级等，有问题就小修一下。最后用[EPUBCheck](https://github.com/w3c/epubcheck)做工具验证，它可以作为Sigil的插件使用，也可以单独使用命令行，在github官方releases页面下载即可。

**第6步：KindlePreviewer预览。**经过第5步，我们得到了精修的epub，在官网下载[Kindle Previewer](https://kdp.amazon.com/en_US/help/topic/G202131170)软件，打开做好的epub，预览一下如果没问题就可以直接send-to-kindle了
