---
title:       "yarn startでブラウザを開かせない方法"
subtitle:    ""
description: "start.jsを編集"
date:        2021-08-15
author:      "Kazuma Kano"
image:       true
tags:        [react]
categories:  [web]
published:   true
---

[React](https://ja.reactjs.org/)では`yarn start`あるいは`npm start`コマンドで開発サーバを起動します。

このとき、既にChromeのウィンドウがあればそのウィンドウに移動し、なければ新しいウィンドウが開かれます。
別の操作スペースだろうと勝手に移動されるので結構鬱陶しいです。
また、別のブラウザをデフォルトのブラウザとして設定していてもChromeが開かれてしまいます。

そこで、`yarn start`を実行してもブラウザを開かせないようにする方法についてまとめます。

# Edit start.js

Reactのプロジェクトディレクトリで`yarn start`を実行すると、コンソールに`$ react-scripts start`と表示されます。
react-scriptsパッケージの`start.js`というスクリプトが呼び出されているようです。

そこで、呼び出されているスクリプトを編集します。

まず、エディタで`node_modules/react-scripts/scripts/start.js`を開きます。
続いて、以下の文をコメントアウトして保存します。
```js
openBrowser(urls.localUrlForBrowser);
```

これで、yarn startでブラウザを開かせないようにすることができました。
