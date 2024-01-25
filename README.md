# Shikimori Search

![GitHub](https://img.shields.io/github/license/noraj/firefox-extension-arch-search)

A set of Web Extensions that adds Shikimori (bug tracker, forum, packages, wiki, AUR, man pages) as
a search engine to the Firefox browser (using the [chrome_settings_overrides](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/chrome_settings_overrides) manifest key).
Submits the query via GET request for compatibility with [Multi-Account Containers](https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/).

Avaible in [AMO](https://addons.mozilla.org/):

| name                       | shortcut | Install                                                                           |
|----------------------------|----------|-----------------------------------------------------------------------------------|
| Shikimori Anime Search     | `shan`   | [AMO](https://addons.mozilla.org/en-US/firefox/addon/shikimori-anime-search/)     |
| Shikimori Articles Search  | `shar`   | [AMO](https://addons.mozilla.org/en-US/firefox/addon/shikimori-articles-search/)  |
| Shikimori Clubs Search     | `shcl`   | [AMO](https://addons.mozilla.org/en-US/firefox/addon/shikimori-clubs-search/)     |
| Shikimori Critiaues Search | `shcr`   | [AMO](https://addons.mozilla.org/en-US/firefox/addon/shikimori-critiaues-search/) |
| Shikimori Forum Search     | `shf`    | [AMO](https://addons.mozilla.org/en-US/firefox/addon/shikimori-forum-search/)     |
| Shikimori Manga Search     | `shm`    | [AMO](https://addons.mozilla.org/en-US/firefox/addon/shikimori-manga-search/)                                                                           |
| Shikimori Ranobe Search    | `shr`    | [AMO](https://addons.mozilla.org/en-US/firefox/addon/shikimori-ranobe-search/)                                                               |
| Shikimori Users Search     | `shu`    | [AMO](https://addons.mozilla.org/en-US/firefox/addon/shikimori-users-search/)                                                                |

# Gratitudes

Many thanks to the [noraj](https://github.com/noraj) for the idea and implementation.


## Install

- Intall from [AMO](https://addons.mozilla.org/) (Available extensions are shown in the table above)
- Manual installation. `npm run buildAll`. And then according to [instrustion](https://wiki.mozilla.org/Installing_Extensions)


## Develop Locally

* Clone the repo
* Install tools:
  * [Node.js](https://nodejs.org) via [asdf](https://asdf-vm.com/)
* Install dependencies:
  * `npm i`
* Lint (check for manifest syntax errors)
  * `npm run lint -- -s web-extensions/v3/<ext-name>`
* Run add-on in isolated Firefox instance using [web-ext](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/Getting_started_with_web-ext) (open the [Browser Toolbox](https://developer.mozilla.org/en-US/docs/Tools/Browser_Toolbox) for console logging):
  * `npm run run -- -s web-extensions/v3/<ext-name>`
* Package for distribution:
  * One extension: `npm run build -- -s web-extensions/v3/<ext-name>`
  * All extensions: `npm run buildAll`

## FAQ

- [Why is there one extension per search engine?](https://stackoverflow.com/questions/64304959/is-it-possible-to-add-multiple-search-engines-in-the-same-firefox-web-extension)
- After the installation, I still  don't see the new search enines. Where are there?
  - Disable/Enable the extensions, this will reload them and they'll appear.
- It's possible to add the search engines by clicking the plus button on the search bar, so why an extension?
  - It's  way quicker to install the extension rather than manually adding the search engines. An extension also allows automation.
  - The bug tracker & the forum use advanced search with several parameters so it's not possible to add them manually via the search bar, an extension is mandatory.
