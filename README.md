# VRCX-0 Community Themes

Officially maintained community theme catalog for VRCX-0. The repository is
maintained by the VRCX-0 project, while the themes listed here are community
content.

Catalog URL:

```text
https://raw.githubusercontent.com/Map1en/VRCX-0-Community-Themes/master/themes/index.json
```

## Maintained Themes

- [Trans Theme Example](themes/trans-theme-example/) by Map1en
- [Darkblue Theme](themes/darkblue-theme/) by xiaoBingge114514
- [Aurora Theme](themes/aurora-theme/) by PuddingKC
- [One Dark Theme](themes/one-dark-theme/) by Dreaminko

## Theme Developer Build

Theme authors should download the dedicated VRCX-0 theme developer build from
[package-theme-devkit](https://github.com/Map1en/VRCX-0/actions/workflows/package-theme-devkit.yml).
It is intended for theme CSS development and debugging.

## How The Catalog Works

`themes/index.json` only lists theme ids. VRCX-0 then loads metadata from each
theme directory:

```text
themes/
  index.json
  <theme-id>/
    theme.json
    theme.css
    README.md
    preview.webp
```

VRCX-0 installs a local snapshot of `theme.css`; it should not live-load a
remote CSS file at runtime.

## Preview Generator

Generate quick skeleton previews for VRCX-0 themes and layouts.

Third-party maintained tool: https://vrcx.puddingkc.com/

## Documentation

- Author a theme: `docs/author-guide.md`
- Download the theme developer build:
  [package-theme-devkit](https://github.com/Map1en/VRCX-0/actions/workflows/package-theme-devkit.yml)
- Submit or update a theme: `CONTRIBUTING.md`
- CSS hooks and layer order: `docs/css-hooks.md`
- Compatibility policy: `docs/compatibility.md`
- Manifest examples and schemas: `examples/`, `schemas/`

By submitting a theme to this catalog, the contributor agrees that the submitted
theme follows GPL-3.0-only for VRCX-0 community theme distribution.
