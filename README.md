# react-native-svg-cache
Render SVG images in React Native from an URL or a static file

URL SVG's are cached using react native's Async Storage.

Forked from 'react-native-svg-uri'.
Merge with source code of 'react-native-fast-svg'.

Install library from `npm`

```bash
npm install react-native-svg-cache --save
```

Link library react-native-svg

```bash
react-native link react-native-svg
```

## Props

| Prop | Type | Default | Note |
|---|---|---|---|
| `source` | `ImageSource` |  | Same kind of `source` prop that `<Image />` component has
| `svgXmlData` | `String` |  | You can pass the SVG as String directly
| `fill` | `Color` |  | Overrides all fill attributes of the svg file
| `fillAll` | `Boolean` |  Adds the fill color to the entire svg object
| `fillAll` | `Boolean` | false | Adds the fill color to the entire svg object
| `noCache` | `Booleean` | false | will not cache this particular SVG if true

## Known Bugs

- [ANDROID] There is a problem with static SVG file on Android,
  Works OK in debug mode but fails to load the file in release mode.
  At the moment the only workaround is to pass the svg content in the svgXmlData prop.

## <a name="Usage">Usage</a>

Here's a simple example:

```javascript
import SvgUri from 'react-native-svg-cache';

const TestSvgUri = () => (
  <View style={styles.container}>
    <SvgUri
      width="200"
      height="200"
      source={{uri:'http://thenewcode.com/assets/images/thumbnails/homer-simpson.svg'}}
    />
  </View>
);
```

or a static file

```javascript
<SvgUri width="200" height="200" source={require('./img/homer.svg')} />
```

This will render:

![Component example](./screenshoots/sample.png)

## Testing
1. Make sure you have installed dependencies with `npm i`
2. Run tests with `npm test`
