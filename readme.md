À mettre dans le .zprofile :

```sh
# TEXLIVE
export TEXLIVE_HOME="/usr/local/texlive/2024basic"
export PATH=$PATH:"/bin/universal-darwin/"
export PATH=$PATH:"/Library/TeX/texbin/"
# END TEXLIVE
```

run sh :

```sh
brew install basictex
curl -o update-tlmgr.sh https://mirror.ibcp.fr/pub/CTAN/systems/texlive/tlnet/update-tlmgr-latest.sh
sudo chmod u+x update-tlmgr.sh
./update-tlmgr.sh
rm -f update-tlmgr.sh

sudo tlmgr update --self
sudo tlmgr update --all
sudo tlmgr install texcount
sudo tlmgr install chktex
sudo tlmgr install synctext
sudo tlmgr install latexindent
sudo tlmgr install latexmk
sudo tlmgr install texdoc
sudo tlmgr install titling
sudo tlmgr install subfiles
sudo tlmgr install lm
sudo tlmgr install cm-super

sudo chown -R $USER /usr/local/texlive
```

Supprimer vscode pdf

installer latex workshop

À mettre dans le setting.json de vscode

```json
"latex-workshop.synctex.path": "/Library/TeX/texbin/synctex",
  "latex-workshop.kpsewhich.path": "/Library/TeX/texbin/kpsewhich",
  "latex-workshop.latex.outDir": "%TMPDIR%",
  "latex-workshop.latex.autoClean.run": "onSucceeded"
```
