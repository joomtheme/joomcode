# JED preparation checklist

Release reviewed on 20 July 2026.

## Package and manifest

- Installable manifest is `package/joomcode.xml`.
- Manifest filename, plugin element, service provider configuration, namespace, and language filenames agree on `joomcode` / `plg_content_joomcode`.
- Release date uses day-month-year format: `20 July 2026`.
- GPLv2-or-later license tag and XML license notice are present.
- Update server and changelog URLs are HTTPS URLs hosted in this repository.
- The ZIP root contains the Joomla manifest and only installable extension files.

## PHP checks

- Every PHP file contains a GPLv2-or-later notice.
- Every PHP file contains the `_JEXEC` restricted-access guard.
- PHP syntax is validated by `scripts/validate.sh`.
- No encoded source, `error_reporting(0)`, shell execution, or deprecated Joomla asset-loading API is used in the installable package.

## Joomla architecture

- Namespaced content plugin with `services/provider.php`.
- `SubscriberInterface` and `ContentPrepareEvent` are used.
- Frontend execution is restricted to the site client.
- Assets are registered and loaded through Joomla Web Asset Manager.
- Joomla's existing administrator form layouts and Bootstrap switcher layout are retained.

## Assets and licensing

- First-party JavaScript and CSS files include copyright and GPL notices.
- PrismJS 1.30.0 is bundled under MIT and includes its upstream license file.
- `joomla.asset.json` is valid JSON and references existing files.

## Update metadata

- Update XML includes plugin `folder` and `client` values.
- Supported target platforms are Joomla 5.x and 6.x.
- Minimum PHP version is 8.1.
- SHA-256, SHA-384, and SHA-512 hashes are generated from the release ZIP.
