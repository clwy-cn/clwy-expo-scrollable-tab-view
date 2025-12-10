
## clwy-expo-scrollable-tab-view

## Add it to your project

Run 
```
npx expo install react-native-pager-view clwy-expo-scrollable-tab-view
```

## Demo

## Basic usage

```javascript
import { StyleSheet, Text } from 'react-native'
import ScrollableTabView, { ScrollableTabBar } from 'clwy-expo-scrollable-tab-view'

export default function Index() {
  return (
    <ScrollableTabView
      style={styles.container}
      initialPage={0}
      renderTabBar={() => <ScrollableTabBar />}
      tabBarUnderlineStyle={styles.barUnderLine}
      tabBarBackgroundColor={'#fff'}
      tabBarInactiveTextColor={'#777'}
      tabBarActiveTextColor={'#000'}
      tabBarTextStyle={styles.barText}
    >
      <Text tabLabel="新闻">新闻的内容</Text>
      <Text tabLabel="体育">体育的内容</Text>
      <Text tabLabel="生活">生活的内容</Text>
      <Text tabLabel="娱乐">娱乐的内容</Text>
      <Text tabLabel="科技">科技的内容</Text>
      <Text tabLabel="创业">创业的内容</Text>
      <Text tabLabel="教育">教育内容</Text>
      <Text tabLabel="财经">财经的内容</Text>
    </ScrollableTabView>
  )
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
  },
  barUnderLine: {
    backgroundColor: '#1f99b0',
    height: 2,
  },
  barText: {
    fontWeight: '400',
  },
})
```

## Props

- **`renderTabBar`** _(Function:ReactComponent)_ - accept 1 argument `props` and should return a component to use as
  the tab bar. The component has `goToPage`, `tabs`, `activeTab` and
  `ref` added to the props, and should implement `setAnimationValue` to
  be able to animate itself along with the tab content. You can manually pass the `props` to the TabBar component.
- **`tabBarPosition`** _(String)_ Defaults to `"top"`.
  - `"bottom"` to position the tab bar below content.
  - `"overlayTop"` or `"overlayBottom"` for a semitransparent tab bar that overlays content. Custom tab bars must consume a style prop on their outer element to support this feature: `style={this.props.style}`.
- **`onChangeTab`** _(Function)_ - function to call when tab changes, should accept 1 argument which is an Object containing two keys: `i`: the index of the tab that is selected, `ref`: the ref of the tab that is selected
- **`onScroll`** _(Function)_ - function to call when the pages are sliding, should accept 1 argument which is an Float number representing the page position in the slide frame.
- **`locked`** _(Bool)_ - disables horizontal dragging to scroll between tabs, default is false.
- **`initialPage`** _(Integer)_ - the index of the initially selected tab, defaults to 0 === first tab.
- **`page`** _(Integer)_ - set selected tab(can be buggy see  [#126](https://github.com/brentvatne/react-native-scrollable-tab-view/issues/126)
- **`children`** _(ReactComponents)_ - each top-level child component should have a `tabLabel` prop that can be used by the tab bar component to render out the labels. The default tab bar expects it to be a string, but you can use anything you want if you make a custom tab bar.
- **`tabBarUnderlineStyle`** _([View.propTypes.style](https://facebook.github.io/react-native/docs/view.html#style))_ - style of the default tab bar's underline.
- **`tabBarBackgroundColor`** _(String)_ - color of the default tab bar's background, defaults to `white`
- **`tabBarActiveTextColor`** _(String)_ - color of the default tab bar's text when active, defaults to `navy`
- **`tabBarInactiveTextColor`** _(String)_ - color of the default tab bar's text when inactive, defaults to `black`
- **`tabBarTextStyle`** _(Object)_ - Additional styles to the tab bar's text. Example: `{fontFamily: 'Roboto', fontSize: 15}`
- **`style`** _([View.propTypes.style](https://facebook.github.io/react-native/docs/view.html#style))_
- **`contentProps`** _(Object)_ - props that are applied to root `ScrollView`/`ViewPagerAndroid`. Note that overriding defaults set by the library may break functionality; see the source for details.
- **`scrollWithoutAnimation`** _(Bool)_ - on tab press change tab without animation.
- **`prerenderingSiblingsNumber`** _(Integer)_ - pre-render nearby # sibling, `Infinity` === render all the siblings, default to 0 === render current page.

## Contribution
**Issues** are welcome. Please add a screenshot of bug and code snippet. Quickest way to solve issue is to reproduce it on one of the examples.

**Pull requests** are welcome. If you want to change API or making something big better to create issue and discuss it first. Before submiting PR please run ```eslint .``` Also all eslint fixes are welcome.

Please attach video or gif to PR's and issues it is super helpful.

<a href="http://www.abeautifulsite.net/recording-a-screencast-with-quicktime/" target="_blank">How to make video</a>

<a href="https://github.com/jclem/gifify" target="_blank">How to make gif from video</a>

---

**MIT Licensed**
