# xcode-notarizer

## About

This action uses `xcrun notarytool` to send your product to Apple's notary service, and `xcrun stapler` to staple the product.

This action supports `.dmg`, `.pkg` file and `.app` folder.

## Quick example

### Submit with Apple ID and app password

```yaml
- name: Notarize product
  uses: love-actions/xcode-notarizer@v1
  with:
    product-path: ./dist/my_app.app
    apple-id: ${{ secrets.APPLE_ID }}
    app-password: ${{ secrets.APP_PASSWORD }}
    team-id: ${{ secrets.TEAM_ID }}
    staple: false
```

### Submit with App Store Connect API key

```yaml
- name: Notarize product
  uses: love-action/xcode-notarizer@v1
  with:
    product-path: ./dist/my_app.app
    key-content: ${{ secrets.API_KEY }}
    key-id: ${{ secrets.API_ID }}
    issuer-id: ${{ secrets.ISSUER_ID }}
    staple: false
```

## All inputs

| Name             | Required  | Default    | Description                                                  |
| :--------------- | --------- | ---------- | ------------------------------------------------------------ |
| `product-path` | `true`  | `""`     | Path to the product. Support `.dmg`, `.pkg` and `.app` |
| `apple-id`     | `false` | `""`     | Apple ID of the product's developer                          |
| `app-password` | `false` | `""`     | App specific password of the product                         |
| `team-id`      | `false` | `""`     | Developer team ID of the product                             |
| `key-content`  | `false` | `""`     | Content of the App Store Connect API key                     |
| `key-id`       | `false` | `""`     | ID of the App Store Connect API key                          |
| `issuer-id`    | `false` | `""`     | ID of the App Store Connect API issuer                       |
| `staple`       | `false` | `"true"` | Whether to staple product or not                             |
