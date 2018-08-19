```
cnpm install antd-mobile --save
```

按需加载

```
 yarn add babel-plugin-import --save-dev
```

```
"babel": {
    "presets": [
      "react-app"
    ],
    "plugins": [
      [
        "import",
        {
          "libraryName": "antd-mobile",
          "style": "css"
        }
      ]
    ]
  },
```

配置

```
yarn eject
```

redux安装

```
yarn add redux --save
```

Redux处理异步工具以及更优雅的和React结合

```
yarn add redux-thunk
yarn add redux-devtools-extension
yarn add react-redux
yarn add babel-plugin-transform-decorators-legacy
```

```
"babel": {
    "presets": [
      "react-app"
    ],
    "plugins": [
      "transform-decorators-legac",
      [
        "import",
        {
          "libraryName": "antd-mobile",
          "style": "css"
        }
      ]
    ]
  },
```

Redux Chrome扩展

Redux DevTools

