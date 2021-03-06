V. I. Arnold: Problems for children from 5 to 15
================================================

This repository contains the LaTeX sources of the translations of Arnold's famous book "Problems for children from 5 to 15" derived from the Russian original http://www.mccme.ru/free-books/izdano/2004/VIA-taskbook.pdf. The book is part of IMAGINARY, a project by the Mathematisches Forschungsinstitut Oberwolfach, supported by the Klaus Tschira Stiftung.

![V. I. Arnold](https://raw.github.com/IMAGINARY/Arnold5to15/master/resources/photo-arnold_small.jpg "V. I. Arnold")

The material in this repository is available under the Creative Commons BY-NC-SA 3.0 license (http://creativecommons.org/licenses/by-nc-sa/3.0/)

Compiling the documents
-----------------------

Since the book is available in serveral languages, we decided to use the XeLaTeX engine. It directly supports unicode and eases font loading. This frees us from the usual LaTeX input/font encoding issues. 

You can use the command line
```
xelatex 5to15_xx_YY.tex 
```
where `xx` is the [language code](http://www.langtag.net/registries/lsr-language.txt) and `YY` is the [region code](http://www.langtag.net/registries/lsr-region.txt) to create `5to15_xx_YY.pdf`. Usually, you can also configure the TeX editor of your choice to use XeLaTeX instead of pdfLaTeX.

Note that the documents rely on a number of recent packages. Therefore:

*Please make sure that you are using a relatively recent TeX distribution.*

You can also consult the file `preamble.tex` for a list of used packages. `preamble.tex` is shared by all the different translations.

Contributing
------------

We encourage you to add translations for new languages and to improve existing ones. Note that your contributions will be published under the above license.

### Adding a translation

First create a new file called `5to15_xx_YY.tex`, where `xx_YY` is substituted according to the above specification. You should do so by copying one of the other translations, e.g. `5to15_en_GB.tex`. Since we are using the Computer Modern Unicode fonts in conjunction with XeLaTeX, you should be able to write down most of the UTF-8 characters directly without using special LaTeX notation, i.e. write `ü` instead of `\"u`. The same is true for Cyrillic, Greek, ... letters. Nevertheless, there may be other font/encoding problems we are currently not aware of. Note that your TeX editor needs to be capable of editing UTF-8 documents as well. It may be necessary to set the UTF-8 encoding (without byte order mark) when loading and/or saving the file.

One of the first lines of your new (copied) file contains the definition of the main language of the file. You need to adjust `\setdefaultlanguage[variant=british]{english}` (in case you did copy `5to15_en_GB.tex`) to reflect the new language. See the list of supported languages in the [polyglossia](http://www.ctan.org/pkg/polyglossia) package.

Now you are ready to translate the document. Please keep your document structure and LaTeX source (math/figures) as close as possible to the other translations. We usually use a visual diff and merge tool to have the original and the new translation side by side. Using e.g. [meld](http://meldmerge.org/) it looks like this:

![Side-by-side editing using meld](https://raw.github.com/IMAGINARY/Arnold5to15/gh-pages/images/meld.png "Side-by-side editing using meld")

Using the side-by-side editing also avoids many common erros, e.g. you will notice inline math you messed up by accident due to the highlighted changes.

During the translation of the text from one language to another you should also consider to review a third translation as well since translations are usually not literal. Try to stay close to the original version although this may not always be possible. The order of the first translations was:
```
Russian -> English -> German
              |          |
              |          V
              +-----> Vietnamese
              |
              +-----> Spanish
              |              
              +-----> Turkish
```
Hence, you should base your translation on a language that is as close as possible to the Russian original in the tree.

Please also add your name(s) to the list of contributors at the end of the document. 

### Improving existing translations

You found a typo? You think, the translation of one of Arnold's problems is wrong or you can improve it? You want to rebuild one (or all) of the graphics in LaTeX (e.g. TikZ)? [Report the issue on GitHub](https://github.com/IMAGINARY/Arnold5to15/issues/new) or [contact us directly](http://www.imaginary.org/contact).

### Using git and GitHub

In order to keep track of your changes, we highly recommend using the git version control system on GitHub. Ideally, you will fork this repository into your GitHub account, clone it to your local system, apply your changes to the documents, commit and push everything to GitHub and finally make a pull request so that we can check your modifications and merge them with the master branch.

### New to XeLaTeX, git and GitHub?

Well, learning new tools is always worth it ;-)
