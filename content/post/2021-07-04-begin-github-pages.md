---
layout:      post
title:       "GitHub Pagesを始める"
subtitle:    ""
description: "無料でサイトを公開する"
author:      "Kazuma Kano"
date:        2021-07-10
image:       true
categories:  [ web ]
tags:
    - github
published: true
---

GitHub Pagesを利用してユーザサイトを公開する方法についてまとめます。

# GitHub Pages
[GitHub Pages](https://pages.github.com/)はGitHubが提供している静的なサイトホスティングサービスです。
[WordPress](https://ja.wordpress.org/)のようなCMSには対応していません。

最低限必要となるのは以下の2つです。
- GitHubアカウント
- サイトのソースコード

GitHub Pagesでサイトをホスティングするには、そのソースコードをGitHubのリポジトリに置く必要があります。
リポジトリごとに1つまでのサイトをホスティングできます。
また、任意のブランチのルートディレクトリあるいは`/docs`ディレクトリをサイトのベースとして設定できます。

カスタムドメインを持っている場合はそれを使用することもできますが、デフォルトのドメインは`username.github.io`です。
デフォルトのドメイン使用時には勝手にHTTPS経由で配信してくれます。

GitHub PagesのサービスはFreeプランでも利用できます。

詳しくは[公式のドキュメント](https://docs.github.com/ja/pages)を参照してください。

# Create Repository
まずはリポジトリを作成します。

Repositories > New を選択すると以下のような画面が表示されます。
ここでリポジトリの初期設定を行います。
リポジトリ名はサイトのURLの一部になります。
これらの設定は後からでも変更できます。
![Create a new repository](../../img/post-20210710-01.png)

# Push Source Code
続いて、サイトのソースコードをプッシュします。

ソースコードを管理しているディレクトリに移動します。
ベースの`index.html`は`dirname`ディレクトリの直下あるいは`dirname/docs`ディレクトリに置いてある必要があります。
```sh
cd dirname
```

Gitの設定ファイルを生成します。
```sh
git init
```

コミットします。
```sh
git add *
git commit -m "first commit"
```

プッシュします。
```sh
git branch -m main 
git remote add origin https://github.com/username/repositoryname.git
git push -u origin main
```

# Publish
最後に、リポジトリのGitHub Pagesサービスを有効化してサイトを公開します。

Repositories > repositoryname > Settings > Pages を選択すると以下のような画面が表示されます。
サイトのベースとなるブランチとディレクトリを設定し、Save を選択します。
![GitHub Pages](../../img/post-20210710-02.png)

数分後、`https://username.github.io/repositoryname/`にアクセスするとサイトが配信されていることが確認できます。
