<a href="https://pix.joseli.to">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/readme/header-dark.svg">
    <img src=".github/readme/header.svg" width="100%" alt="pix.joseli.to">
  </picture>
</a>

&nbsp;

Se algo que eu fiz te ajudou, um Pix de qualquer valor ajuda a manter os projetos no ar.

*If something I made helped you, a Pix of any amount helps keep the projects running.*

## Pix

<picture>
  <source media="(prefers-color-scheme: dark)" srcset=".github/readme/qr-dark.svg">
  <img src=".github/readme/qr.svg" width="280" alt="QR Code Pix para apoie@pix.joseli.to · Pix QR code for apoie@pix.joseli.to">
</picture>

Aponte a câmera do app do banco. O valor fica a seu critério.<br>
*Point your bank app's camera at the code. The amount is up to you.*

**Chave Pix (e-mail)** · *Pix key (email)*

```
apoie@pix.joseli.to
```

**Pix copia e cola** · *Pix copy and paste*

```
00020126410014br.gov.bcb.pix0119apoie@pix.joseli.to5204000053039865802BR5908Joselito6006Recife62070503***6304CCF5
```

## Outras formas · Other ways

<a href="https://buymeacoffee.com/joselito">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/readme/coffee-dark.svg">
    <img src=".github/readme/coffee.svg" width="380" alt="Buy Me a Coffee">
  </picture>
</a>
<br>
<a href="https://github.com/sponsors/breakzplatform">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/readme/sponsors-dark.svg">
    <img src=".github/readme/sponsors.svg" width="380" alt="GitHub Sponsors">
  </picture>
</a>

## Código · Source

A página é um único HTML estático, sem rastreadores nem JavaScript externo. *The page is a single static HTML file, with no trackers and no external JavaScript.*

- `template.html`: a página, com os marcadores que o build preenche. *The page, with the placeholders the build fills in.*
- `build.py` (precisa de [uv](https://docs.astral.sh/uv/)): gera `site/index.html`, monta o BR Code estático (EMV, sem valor), confere o CRC16, embute o QR em SVG e fixa os scripts inline na CSP por hash. *Renders `site/index.html`: builds the static BR Code (EMV, no amount), checks its CRC16, inlines the QR as SVG and pins the inline scripts in the CSP by hash.*
- `scripts/build-social.sh`: gera a prévia de link `site/og.png` com o Chrome. *Renders the link preview `site/og.png` with Chrome.*
- `bin/deploy`: publica `site/` como o Cloudflare Worker em `pix.joseli.to/*`, com os cabeçalhos de `site/_headers`. Roda sozinho pelo GitHub Actions a cada push na `main`. *Publishes `site/` as the Cloudflare Worker on `pix.joseli.to/*`, with the headers from `site/_headers`. GitHub Actions runs it on every push to `main`.*

```sh
./build.py                                   # gera site/index.html · renders site/index.html
CLOUDFLARE_API_TOKEN=... ./bin/deploy        # publica · deploys
```

## Licença · License

O código da página é GPL-3.0-only ([LICENSE](LICENSE)). As imagens deste README, em [`.github/readme/`](.github/readme), continuam MIT ([licença](.github/readme/LICENSE)). *The page code is GPL-3.0-only. The README images in `.github/readme/` stay MIT.*
