# /fazervideo

**Português** · [English](#english)

Uma skill do Claude Code que faz vídeo do seu produto do zero: tutorial com a tela real do app,
lançamento, anúncio, vinheta, corte para Reels. Ela lê o seu projeto, grava as telas, anima em código,
compõe uma trilha original e entrega o MP4 (16:9, 9:16, 1:1 ou 4:5). O vídeo fala por legenda e música.
Sem API externa: imagem e trilha saem da sua máquina.

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

---

## English

A Claude Code skill that makes a video of your product from scratch: a tutorial with the real app screen, a launch,
an announcement, a logo sting, a cut for Reels. It reads your project, records the screens, animates in code,
composes an original soundtrack and delivers the MP4 (16:9, 9:16, 1:1 or 4:5). The video speaks through captions
and music. No external API: visuals and music are generated on your machine.

Want a voice narrating? Use [/fazervideocomvoz](https://github.com/svcrashh/fazervideocomvoz), which ships this engine
inside.

It talks to you in Portuguese or English, whichever you use. Its internal references are written in Portuguese;
Claude reads them and answers in your language.

### Install

```sh
# Mac and Linux
git clone https://github.com/svcrashh/fazervideo ~/.claude/skills/fazervideo
```

```powershell
# Windows
git clone https://github.com/svcrashh/fazervideo "$HOME\.claude\skills\fazervideo"
```

Open Claude Code in your project and ask for `/fazervideo`, or "make a tutorial video of …".

### What your machine needs

Node.js 18 or newer, Python 3, ffmpeg and Playwright's Chromium. You don't need to install anything first: on the
first run the skill checks what's missing, shows the right command for your system, and only installs with your
permission.

To get ahead:

- **Mac** (with Homebrew): `brew install node python ffmpeg`
- **Windows** (PowerShell): `winget install OpenJS.NodeJS.LTS`, `winget install Python.Python.3.12`,
  `winget install --id Gyan.FFmpeg -e`

The final render is heavy (a few minutes per video). On a laptop, keep it plugged in.

### How it works

1. Asks what kind of video it is and reads your project: brand, colors, fonts, audience.
2. Runs the briefing (where it will play, length, music) and pitches three ideas.
3. Records the real screen with Playwright, never clicking anything that's covered, and blurs what's private.
4. Animates in HTML/SVG frame by frame, with motion blur, and composes the soundtrack in code.
5. Shows you a draft with sound. Only after your OK does it render the final.

The full documentation (in Portuguese) is in [`SKILL.md`](SKILL.md) and [`references/`](references/).

### License

[MIT](LICENSE).
