# /fazervideo

Uma skill do Claude Code que faz vídeo do seu produto do zero: tutorial com a tela real do app,
lançamento, anúncio, vinheta, corte para Reels. Ela lê o seu projeto, grava as telas, anima em código,
compõe uma trilha original e entrega o MP4 (16:9, 9:16, 1:1 ou 4:5). O vídeo fala por legenda e música.

Quer uma voz narrando? Use a [/fazervideocomvoz](https://github.com/svcrashh/fazervideocomvoz), que traz
este motor dentro.

## Instalar

```sh
# Mac e Linux
git clone https://github.com/svcrashh/fazervideo ~/.claude/skills/fazervideo
```

```powershell
# Windows
git clone https://github.com/svcrashh/fazervideo "$HOME\.claude\skills\fazervideo"
```

Abra o Claude Code no seu projeto e peça `/fazervideo`, ou "faz um vídeo tutorial de …".

## O que precisa ter na máquina

Node.js 18 ou mais novo, Python 3, ffmpeg e o Chromium do Playwright. Não precisa instalar nada antes:
na primeira vez a skill confere o que falta e mostra o comando certo para o seu sistema, e só instala
com a sua autorização.

Se quiser adiantar:

- **Mac** (com Homebrew): `brew install node python ffmpeg`
- **Windows** (PowerShell): `winget install OpenJS.NodeJS.LTS`, `winget install Python.Python.3.12`,
  `winget install --id Gyan.FFmpeg -e`

O render final é pesado (alguns minutos por vídeo). Em notebook, deixe na tomada.

## Como ela trabalha

1. Pergunta que tipo de vídeo é e lê o seu projeto: marca, cores, fontes, público.
2. Faz o briefing (onde passa, duração, música) e propõe três ideias.
3. Grava a tela real com Playwright, sem tocar em nada que esteja coberto, e borra o que é privado.
4. Anima em HTML/SVG quadro a quadro, com motion blur, e compõe a trilha em código.
5. Mostra um rascunho com som. Só depois do seu ok faz o render final.

A documentação completa está em [`SKILL.md`](SKILL.md) e em [`references/`](references/).

## Licença

[MIT](LICENSE).
