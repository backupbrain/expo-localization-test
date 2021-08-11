# expo-localization-test

Test the Translation and Localization of text, numbers, and date

## Features

We need to test the following features:

Importantly there needs to be 6 features

1. `a String translate(String key, Object vars=null)` function that takes a `String key` and returns the text from the current app's language. Therefore all text will pass through the translator. `vars` should default to `null` or should be ignored if not provided.
2. If a vars object is passed into `translate()`, the `translate()` function should replace the `key`s in `var`s matching `{key}` in the translation package.  For example, `translate('hello', {name: 'John'})` should resolve  `"Hello {name},"` into `Hello John,`.
3. The app should default to the OS locale, and fall back to en if there are no translations available for the OS locale.  For example, if the OS is `ru` and there are translations available in `ru`, the app will default to `ru`. But if the OS is in `sw` and no translation is available, the app will default to `en`
4. The system should be able to switch languages and locales on the fly. all text should translate and all numbers should localize immediately into the new locale when the switch is made.
5. All dates and number formats will localize to the current locale if available. The number `1000.000` will localize to `1,000.000` for `en` and will localize to `1.000,00` for `fr`.  `October 11, 2021` will localize to `11/10/2021` for `en-US` and will localize to `2012-11-10` for `fr`. Therefore all numbers, dates, and times will pass through the localizer.
6. In some instances, it will be important to show the significant figures and suffix of large numbers, for example `12345678.34303453`  will become `1.2m`

Possible solutions to this; 
* https://stackoverflow.com/questions/9461621/format-a-number-as-2-5k-if-a-thousand-or-more-otherwise-900
* https://stackoverflow.com/questions/25416635/display-number-with-significant-figures-and-k-m-b-t-suffix-in-javascript

## Testing:

**Test Language Packs:**

Language packs are in the `translations/` folder.

Format:
```json
{
  "key": "Localized text with {optional} {variables}"
}
```

`en.json`:
```json
{
 "hello": "Hello {name},",
 "niceToMeetYou": "Nice to meet you."
}
```
`gr.json`:
```json
{
 "hello": "Τι κάννεις {name},",
 "niceToMeetYou": "Χάρικα πολύ."
}
```
**Test dates:**

October 11, 2021

Test Times:

1:30pm

**Test Numbers:**

1234
1234.56
123456789.232342342
0.0002343



## Follow these tutorials:

[i18n With React Native](http://www.reactnative.com/i18n-with-react-native/)
[React Native localization and internationalization](https://lokalise.com/blog/react-native-localization/)

[How to translate in React Native app— Globalization, Internationalization, and Text to Speech](https://enappd.com/blog/how-to-translate-in-react-native-app-globalization-internationalization-and-text-to-speech/120/)

[Internationalization and localization in React Native](https://blog.logrocket.com/internationalization-and-localization-in-react-native/)

## Use the `react-native-localize` module:

This module has specific installation instructions, especially on mobile. Make sure to follow the **Manual Linking** section.

[react-native-localize](https://github.com/zoontek/react-native-localize)
