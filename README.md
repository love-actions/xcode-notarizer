# xcode-notarizer

## About

Github Action for building & deploying Linux `.AppImage` packages of a [LÖVE](https://love2d.org/) framework based game.

### Related actions

See related actions below:

[Love actions bare package](https://github.com/marketplace/actions/love-actions-bare-package)

[Love actions for testing](https://github.com/marketplace/actions/love-actions-for-testing)

[Love actions for android](https://github.com/marketplace/actions/love-actions-for-android)

[Love actions for iOS](https://github.com/marketplace/actions/love-actions-for-ios)

[Love actions for macOS portable](https://github.com/marketplace/actions/love-actions-for-macos-portable)

[Love actions for macOS AppStore](https://github.com/marketplace/actions/love-actions-for-macos-appstore)

[Love actions for Windows](https://github.com/marketplace/actions/love-actions-for-windows)

## Quick example

```yaml
- name: Build Linux packages
  id: build-packages
  uses: 26F-Studio/love-actions-linux@main
  with:
    desktop-file-path: ./.github/build/linux/dev/template.desktop
    executable-name: app
    icon-path: ./.github/build/linux/dev/icon.png
    love-package: ./game.love
    product-name: love_app
    output-folder: "./dist"
```

## All inputs

| Name           | Required | Default         | Description                                                  |
| :------------- | -------- | --------------- | ------------------------------------------------------------ |
| `product-path` | `false`  | `""`            | Path to the `.desktop` file, see [Desktop integration](https://docs.appimage.org/reference/desktop-integration.html). Use LÖVE default if not specified |
| `apple-id`     | `false`  | `"love"`        | Executable name. Used as appImage's internal executable filename |
| `app-password` | `false`  | `""`            | Path to the appImage's icon. Use LÖVE default if not specified |
| `team-id`      | `false`  | `"./game.love"` | Love package. Used to assemble the executable                |
| `staple`       | `false`  | `"love_app"`    | Base name of the package. Used to rename products            |
