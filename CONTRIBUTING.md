# Contributing Themes

Thank you for contributing a VRCX-0 community theme.

This repository is officially maintained by the VRCX-0 project, but submitted themes are community-authored content. Please make sure your theme is reviewable, redistributable, and safe to use.

## Tools

To debug CSS, download the dedicated theme developer build from:

https://github.com/Map1en/VRCX-0/actions/workflows/package-devkit.yml

You can also generate quick skeleton previews with the third-party maintained preview generator:

https://vrcx.puddingkc.com/

## Writing a Theme

Use a lowercase kebab-case theme directory name:

```text
themes/<theme-id>/
  theme.json
  theme.css
  README.md
  preview.webp
```

A theme must include:

* `theme.json`
* `theme.css`
* `README.md`
* `preview.webp`

The theme directory name must match `theme.json` `id`.

Start from `examples/theme.example.jsonc`, then remove comments and save it as strict JSON.

`theme.json` is machine-readable metadata. `theme.css` is the CSS installed by VRCX-0. `README.md` should be a short user-facing theme introduction that can be shown in the app.

`preview.webp` must use that exact file name and WebP format. Keep it compressed, stripped of unnecessary metadata, and no larger than 256 KiB.

After adding the theme directory, add only the theme id string to `themes/index.json`.

Also add your theme to the `Maintained Themes` section in the repository root `README.md`:

```md
## Maintained Themes

- [Trans Theme Example](themes/trans-theme-example/) by Map1en
```

## Manifest Fields

* `id`: stable lowercase slug. Must match the theme directory name.
* `version`: semantic version, starting at `1.0.0`.
* `author.github`: required GitHub username.
* `author.url`: optional personal site or profile link.
* `tags`: one to three short tags.
* `testedWith`: latest VRCX-0 version tested by the author.
* `remoteAssets`: `true` if the CSS references remote images or fonts.
* `darkMode`: `true` if based on VRCX-0 dark mode, otherwise `false`.
* `accentMode`: `true` if users can still use VRCX-0's built-in accent color selector, otherwise `false`.

## CSS Policy

Allowed:

* App-owned surface variables documented in `docs/css-hooks.md`.
* Ordinary CSS selectors.
* Tailwind/shadcn class overrides, with the understanding that they are not stable.
* External image or font URLs when `remoteAssets` is `true`.

Not allowed:

* CSS that hides or disables recovery, close, exit, login, confirmation, or destructive-action UI.
* CSS intended to mislead users about app state or identity.
* Remote `@import` of CSS files.
* JavaScript, HTML, browser extension code, or build output.
* Minified, generated, encrypted, or intentionally unreadable CSS.

## Remote Assets

Remote images and fonts are allowed when `remoteAssets` is `true`.

Theme authors are responsible for using assets they have permission to reference or redistribute. Remote assets may fail, change, or expose user IP address and user agent to the asset host.

If externally linked assets or CSS are believed to infringe someone's rights, please open an issue for review.

## Compatibility

VRCX-0 may change page structure and styling over time. App development takes priority, and themes are not guaranteed to stay compatible across future versions.

`testedWith` only records the latest VRCX-0 version tested by the theme author. It is not a guarantee that the theme works on every future version.

## Pull Request Rules

* One pull request should add or update one theme.
* Do not modify another author's theme unless the author requested it or maintainers asked for a compatibility fix.
* A new theme must include all required files.
* The theme directory name must match `theme.json` `id`.
* `themes/index.json` should only add or keep the theme id string.
* The repository root `README.md` should include the theme under `Maintained Themes`.
* The theme must be tested with the latest available VRCX-0 version before submission.
* By submitting a theme, the contributor agrees that the submitted theme follows GPL-3.0-only for VRCX-0 community theme distribution.

## Review Checklist

Before opening a pull request, confirm that:

* `theme.json` is valid strict JSON.
* The theme directory name matches `id`.
* `themes/index.json` contains only the theme id string.
* The root `README.md` includes the theme under `Maintained Themes`.
* `remoteAssets` matches the CSS.
* `darkMode` matches the CSS base mode.
* The UI remains recoverable with the theme enabled.
* `preview.webp` is included and no larger than 256 KiB.
* The preview image only uses assets the author owns, has permission to use, or may redistribute.

## Updating a Theme

Theme updates should bump `version` and update `testedWith` when verified against a newer VRCX-0 version.
