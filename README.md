# @nareshj7/expo-router-v3-top-tabs

Wraps `react-native-collapsible-tab-view` and adds support for [Expo Router v3](https://expo.github.io/router/docs).

## Add the package to your npm dependencies

```
yarn add @nareshj7/expo-router-v3-top-tabs react-native-reanimated
```

- Setup Reanimated in the `babel.config.js`. See [here](https://docs.swmansion.com/react-native-reanimated/docs/fundamentals/getting-started/#step-2-add-reanimateds-babel-plugin) for more info.

- If you face 'setPage' undefined error while using try installing `react-native-pager-view` and `react-native-tab-view`.

## Usage

Example in Layout Route:

```js
// app/(tabs)/_layout.tsx

import { Text, View } from "react-native";
import { TopTabs } from "@nareshj7/expo-router-v3-top-tabs";

export default function CustomLayout() {
  return (
    <TopTabs screenOptions={{}}>
      <TopTabs.Header>
        <View pointerEvents="none" style={{}}>
          <Text>Header</Text>
        </View>
      </TopTabs.Header>

      <TopTabs.Screen name="index" />
    </TopTabs>
  );
}
```

Usage in child routes:

```js
// app/(tabs)/index.tsx

import { Animated } from "react-native";
import { useScrollProps } from "@nareshj7/expo-router-v3-top-tabs";

export default function Screen() {
  const props = useScrollProps();

  return <Animated.ScrollView {...props}></Animated.ScrollView>;
}
```
