[[../Markdown|Markdown]]
## Obsidian Badge Plugin

![GitHub release badge](https://badgen.net/github/release/linjunpop/obsidian-badge)

This is a plugin to render badges in Obsidian ([https://obsidian.md](https://obsidian.md/)).

## Usage

The `obsidian-badge` fenced code blocks will be rendered each line as a embed badge.

```obsidian-badge
Reading - The Flat land: 11/23

Exercise: 77/100
```

```obsidian-badge
My Yearly plan: 29/40
```

which will render

![image](https://user-images.githubusercontent.com/214616/164978149-e968feab-d43c-459f-9180-31ba6a8dce4e.png)

## Installation

### Installing from the Obsidian App

Search "Badge" in Settings -> Community plugins, you can find and install this plugin.

You can check [https://help.obsidian.md/Advanced+topics/Third-party+plugins#Discover+and+install+community+plugins](https://help.obsidian.md/Advanced+topics/Third-party+plugins#Discover+and+install+community+plugins) for an official guide.

### Manually installing the plugin

Find the latest release: [https://github.com/linjunpop/obsidian-badge/releases](https://github.com/linjunpop/obsidian-badge/releases), then copy over `main.js`, `manifest.json` to your vault's `.obsidian/plugins/obsidian-badge` directory (ex. `VaultFolder/.obsidian/plugins/obsidian-badge/`).

## Development

Quick starting guide for new plugin devs:

- Make a copy of this repo as a template with the "Use this template" button (login to GitHub if you don't see it).
- Clone your repo to a local development folder. For convenience, you can place this folder in your `.obsidian/plugins/your-plugin-name` folder.
- Install NodeJS, then run `npm i` in the command line under your repo folder.
- Run `npm run dev` to compile your plugin from `main.ts` to `main.js`.
- Make changes to `main.ts` (or create new `.ts` files). Those changes should be automatically compiled into `main.js`.
- Reload Obsidian to load the new version of your plugin.
- Enable plugin in settings window.
- For updates to the Obsidian API run `npm update` in the command line under your repo folder.

### Releasing new releases

- Update your `manifest.json` with your new version number, such as `1.0.1`, and the minimum Obsidian version required for your latest release.
- Update your `versions.json` file with `"new-plugin-version": "minimum-obsidian-version"` so older versions of Obsidian can download an older version of your plugin that's compatible.
- Create new GitHub release using your new version number as the "Tag version". Use the exact version number, don't include a prefix `v`. See here for an example: [https://github.com/obsidianmd/obsidian-sample-plugin/releases](https://github.com/obsidianmd/obsidian-sample-plugin/releases)
- Upload the files `manifest.json`, `main.js`, `styles.css` as binary attachments. Note: The manifest.json file must be in two places, first the root path of your repository and also in the release.
- Publish the release.

>  
> 
> You can simplify the version bump process by running `npm version patch`, `npm version minor` or `npm version major` after updating `minAppVersion` manually in `manifest.json`.  
> The command will bump version in `manifest.json` and `package.json`, and add the entry for the new version to `versions.json`

### Adding your plugin to the community plugin list

- Check [https://github.com/obsidianmd/obsidian-releases/blob/master/plugin-review.md](https://github.com/obsidianmd/obsidian-releases/blob/master/plugin-review.md)
- Publish an initial version.
- Make sure you have a `README.md` file in the root of your repo.
- Make a pull request at [https://github.com/obsidianmd/obsidian-releases](https://github.com/obsidianmd/obsidian-releases) to add your plugin.

### Manually installing the plugin

- Copy over `main.js`, `styles.css`, `manifest.json` to your vault `VaultFolder/.obsidian/plugins/your-plugin-id/`.

### Improve code quality with eslint (optional)

- [ESLint](https://eslint.org/) is a tool that analyzes your code to quickly find problems. You can run ESLint against your plugin to find common bugs and ways to improve your code.
- To use eslint with this project, make sure to install eslint from terminal:
    - `npm install -g eslint`
- To use eslint to analyze this project use this command:
    - `eslint main.ts`
    - eslint will then create a report with suggestions for code improvement by file and line number.
- If your source code is in a folder, such as `src`, you can use eslint with this command to analyze all files in that folder:
    - `eslint .\src\`

### API Documentation

See [https://github.com/obsidianmd/obsidian-api](https://github.com/obsidianmd/obsidian-api)