# Privacy Policy

Last updated: May 22, 2026

Local Page Media Downloader is a local, user-triggered Chrome/Chromium extension for finding media URLs that are already visible or accessible to the active browser tab.

## Data Collection

The extension does not collect, sell, share, transmit, or store personal data on external servers.

The extension reads the active page only after the user clicks the scan button. It may inspect page HTML, media element attributes, CSS background URLs, metadata media tags, direct media links, and browser resource timing entries for the active tab. This processing happens locally in the browser.

## Data Use

The extension uses discovered media URLs only to show them in the popup and, when the user clicks the download button, to ask Chrome's downloads API to download selected items.

The extension does not run automatic background scans. Downloads never start automatically.

## Data Sharing

No discovered URL, browsing activity, page content, setting, or download list is sent to the developer, analytics services, advertising networks, or any third party.

## Local Settings

The extension may store local popup settings, such as the minimum media size filter and whether unknown-size media should be shown. These settings are stored locally in the browser via `localStorage`.

## Remote Code, Telemetry, and Analytics

The extension does not use remote code, telemetry, analytics, tracking pixels, or external scripts.

## Permissions

- `activeTab`: grants temporary access to the currently active tab after the user interacts with the extension.
- `scripting`: runs the local scan function in the active tab only after the user clicks scan.
- `downloads`: downloads selected media only after the user clicks download.

The extension does not request broad `host_permissions`.

## Limited Use Statement

The use of information received from Chrome APIs will adhere to the Chrome Web Store User Data Policy, including the Limited Use requirements.

## Legal Note

Users are responsible for respecting copyright, licenses, website terms, and applicable law. The extension does not bypass DRM, authentication, paywalls, copyright protections, or protected streaming mechanisms.
