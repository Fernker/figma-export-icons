# figma-export-icons

This was forked from the original `figma-export-icons` package that hasn't been maintained.

## Forked additions

### ExportVariants

In the config you can optionally supply `exportVariants: true` if you want it to export and split the variant/component icon in figma. It will give each icon variant a different named suffix according to variant name.

config property: `exportVariants`

### maxConcurrentConnections

When the amount of icons gets above ~400 it was causing S3 errors (from where Figma hosts the assets). This config param allows you to pass a number value to lower that and to chunk the request in smaller batches.

config property: `maxConcurrentConnections`

### frames

The config `frame` option only allows a single-frame to be defined. You can optionally set the `frames` config option and pass an array of frame names. If it can't find a matching frame you will not get an error like with the single `frame` option.

config property: `frames`

example config file:

```json
{
  "figmaPersonalToken": "YOUR_PERSONAL_TOKEN",
  "fileId": "FILE_ID",
  "page": "Identity",
  "frame": "Icons",
  "frames": ["Optional", "list", "of", "frames"],
  "iconsPath": "assets/svg/icons",
  "removeFromName": "Icon=",
  "exportVariants": true,
  "maxConcurrentConnections": 100
}
```
