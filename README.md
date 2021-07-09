# vuetify-missing-fill-height

Example of a bug in Vuetify that causes the fill-height class to disappear.

## Explanation

I built a barebones application useing `vue/cli@5.0.0-beta.2` with the following commands:

```
vue create vuetify-missing-fill-height
vue add vuetify
```

This created an app with `vue@2.6.14` and `vuetify@2.5.6`.

Then I simply changed the content of `App.vue` so that `<v-main>` contained the [grid example](https://vuetifyjs.com/en/components/images/#grid) from the docs ([also on GitHub](https://github.com/vuetifyjs/vuetify/blob/master/packages/docs/src/examples/v-img/misc-grid.vue)). And then I removed everything from the `v-app-bar` except the logo.

Now, when you run the dev server, the `<v-progress-circular>` components are not vertically centered over the `<v-img>` components when loading. Instead, they are positioned at the top. This is because the `fill-height` class, which is set on the `<v-row>` component containing the `<v-progress-circular>`, does not exist. I have no idea why it is missing. But, if we place the `<v-spacer>` back in the `<v-app-bar>`, then `fill-height` returns and everything is positioned correctly.

To see the `<v-progress-circular>` components position correctly, uncomment line 20 of `App.vue`. With the inspector, you will see that the `fill-height` class has magically returned.

TL;DR: Removing `<v-spacer>` make the `fill-height` class disappear from the stylesheet.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```
