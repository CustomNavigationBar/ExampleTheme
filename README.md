# Example Navbar Theme
This repo contains an example theme for [Custom Navigation Bar](https://play.google.com/store/apps/details?id=xyz.paphonb.systemuituner)

This document will explain the theme format.

A theme consists of

- Intent filter
- Theme Manifest
- Drawables

## Intent filter
Custom Navigation Bar search for themes by searching for activities can responds to the action `xyz.paphonb.systemuituner.THEME`

This can be easily done by adding the following intent filter in your activity.
```
<intent-filter>
    <action android:name="xyz.paphonb.systemuituner.THEME" />
</intent-filter>
```

## Theme manifest
Theme informations can be specified in `res/xml/themes.xml`

The file must have `theme-package` as a root element.

A `theme-package` consists of `theme`s. There can be more than one theme in one `theme-package`

A `theme` must have a `title` attribute, which points to a string resource. Hard-coded strings are not supported.
```
<theme title="@string/theme_name">
```

## Drawables
Replacement drawables can be placed in a `theme`.
```
<item name="to_be_replaced" drawable="@drawable/replacement" />
```
Currently supported drawable replacements are

- `ic_sysbar_back` for back button
- `ic_sysbar_home` for home button
- `ic_sysbar_recent` for recent button

## Final result
A final theme manifest can look like this
```
<?xml version="1.0" encoding="utf-8"?>
<theme-package>
    <theme title="@string/theme_name">
        <item name="ic_sysbar_back" drawable="@drawable/themed_ic_sysbar_back" />
        <item name="ic_sysbar_home" drawable="@drawable/themed_ic_sysbar_home" />
        <item name="ic_sysbar_recent" drawable="@drawable/themed_ic_sysbar_recent" />
    </theme>
</theme-package>
```
Themes are currently supported starting from beta 0.5.5

If you have any issues, feel free to contact me at [paphonb@gmail.com](mailto:paphonb@gmail.com).

Happy theming. :)