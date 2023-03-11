# flutter_tex_js

A lightweight TeX plugin for Flutter based on [KaTeX](https://katex.org/), a
popular and full-featured JavaScript TeX rendering library.

<img width="300" src="https://pbs.twimg.com/media/EdiODWEVAAIZg9-?format=png&name=4096x4096">

_flutter_tex_js used in [Orgro](https://orgro.org)_

_See a [demo video](https://twitter.com/amadlonkay/status/1285937038840131584?s=20)_

# What's different about this plugin?

As of July 2020, there are several other TeX packages/plugins for Flutter, but
most of them are either a) very heavyweight, relying on webview_flutter, or b)
very immature, with poor support for common TeX syntax.

This plugin seeks a middle ground: It uses a single native webview under the
hood, in which it renders TeX markup to PNG. It then sends the PNG bytes back to
the Dart world where the result is displayed as an image.

# Supported platforms

- Android 4.1 (SDK 16) and higher
- iOS 11 and higher*
  - *You can include the plugin on iOS 9+, but it will only render on 11+. On
    iOS 9 and 10, the `TexImage` widget will simply show the supplied text
    as-is.

# Setup

## Android

If your app uses Kotlin, make sure it is v1.3.60 or later (see
`ext.kotlin_version` in your `build.gradle` file). The default is v1.3.50, but
this has [known problems](https://github.com/amake/flutter_tex_js/issues/7), so
if you have never updated your Kotlin version then please do so.

## iOS

No setup required.

# Usage

```dart
import 'package:flutter_tex_js/flutter_tex_js.dart';

class MyMathWidget extends StatelessWidget {
  Widget build(BuildContext context) {
    return TexImage(r'a=\pm\sqrt{b^2+c^2} \int_\infty^\beta d\gamma');
  }
}
```
