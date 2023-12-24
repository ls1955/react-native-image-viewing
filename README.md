## Disclaimer

This fork apply fixes for zoom issue after swiping on Android and inconsistent double tap zooming behavior from [this PR](https://github.com/jobtoday/react-native-image-viewing/pull/191) and [this PR](https://github.com/bluesky-social/social-app/pull/1482).

# react-native-image-viewing

> React Native modal component for viewing images as a sliding gallery.

## Installation
Add this in your package.json:

```js
  "dependencies": {
    "react-native-image-viewing": "git@github.com:ls1955/react-native-image-viewing.git"
  }
```

Then:

```bash
npm install
```

## Usage

```jsx
import ImageView from "react-native-image-viewing";

const images = [
  {
    uri: "https://images.unsplash.com/photo-1571501679680-de32f1e7aad4",
  },
  {
    uri: "https://images.unsplash.com/photo-1573273787173-0eb81a833b34",
  },
  {
    uri: "https://images.unsplash.com/photo-1569569970363-df7b6160d111",
  },
];

const [visible, setIsVisible] = useState(false);

<ImageView
  images={images}
  imageIndex={0}
  visible={visible}
  onRequestClose={() => setIsVisible(false)}
/>
```

#### [See Example](https://github.com/jobtoday/react-native-image-viewing/blob/master/example/App.tsx#L62-L80)

## Props

| Prop name                | Description                                                                                         | Type                                                        | Required |
| ------------------------ | --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- | -------- |
| `images`                 | Array of images to display                                                                          | ImageSource[]                                               | true     |
| `keyExtractor`           | Uniqely identifying each image    | (imageSrc: ImageSource, index: number) => string | false |
| `imageIndex`             | Current index of image to display                                                                   | number                                                      | true     |
| `visible`                | Is modal shown or not                                                                               | boolean                                                     | true     |
| `onRequestClose`         | Function called to close the modal                                                                  | function                                                    | true     |
| `onImageIndexChange`     | Function called when image index has been changed                                                   | function                                                    | false    |
| `onLongPress`            | Function called when image long pressed                                                             | function (event: GestureResponderEvent, image: ImageSource) | false    |
| `delayLongPress`         | Delay in ms, before onLongPress is called: default `800`                                            | number                                                      | false    |
| `animationType`          | Animation modal presented with: default `fade`                                                      | `none`, `fade`, `slide`                                     | false    |
| `presentationStyle`      | Modal presentation style: default: `fullScreen` **Android:** Use `overFullScreen` to hide StatusBar | `fullScreen`, `pageSheet`, `formSheet`, `overFullScreen`    | false    |
| `backgroundColor`        | Background color of the modal in HEX (#000000EE)                                                    | string                                                      | false    |
| `swipeToCloseEnabled`    | Close modal with swipe up or down: default `true`                                                   | boolean                                                     | false    |
| `doubleTapToZoomEnabled` | Zoom image by double tap on it: default `true`                                                      | boolean                                                     | false    |
| `HeaderComponent`        | Header component, gets current `imageIndex` as a prop                                               | component, function                                         | false    |
| `FooterComponent`        | Footer component, gets current `imageIndex` as a prop                                               | component, function                                         | false    |

- type ImageSource = ImageURISource | ImageRequireSource

## Contributing

To start contributing clone this repo and then run inside `react-native-image-viewing` folder:

```bash
yarn
```

Then go inside `example` folder and run:

```bash
yarn & yarn start
```

This will start packager for expo so you can change `/src/ImageViewing` and see changes in expo example app.

## License

[MIT](LICENSE)
