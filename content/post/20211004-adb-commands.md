---
title:       "Android Debug Bridge"
subtitle:    ""
description: "よく使うコマンドまとめ"
date:        2021-10-04
author:      "Kazuma Kano"
image:       true
tags:        [android]
categories:  [util]
published:   true
---

忘れて調べ直すことがあるので、個人的によく使うadbのコマンドをまとめておきます。

# Android Debug Bridge
Android Debug Bridge (adb) はAndroidデバイスと通信するためのコマンドラインツールです。

adbはAndroid SDK Platform-Toolsパッケージに含まれており、[Android Studio](https://developer.android.com/studio?hl=ja)のSDK Managerを介してインストールすることができます。
一応、Android Studioを使わずにSDK Platform-Toolsパッケージ単体でインストールすることも可能なようです。

詳しくは[公式のドキュメント](https://developer.android.com/studio/command-line/adb?hl=ja)を参照してください。

# Developer Options
adbを使うには、あらかじめAndroidデバイス側で開発者向けオプションを有効にしておく必要があります。
設定 > デバイス情報 > ビルド番号 を7回タップすることで開発者向けオプションを有効にできます。

USB経由で通信するには、さらにUSBデバッグを有効にする必要があります。
設定 > システム > 詳細設定 > 開発者向けオプション > USBデバッグ から変更できます。

また、USB経由の他にWi-Fi経由で通信することもできるようです。

# Commands
私が比較的よく使うコマンドは以下です。
- `adb devices`\
接続されているAndroidデバイスの一覧を表示します。
AndroidデバイスがPCに認識されているかどうかの確認にもなります。
- `adb shell`\
Androidデバイス上のUnixシェルにアクセスします。
`exit`コマンドで抜けられます。
- `adb ls dirname`\
指定したディレクトリ内のファイルの一覧を表示します。
- `adb pull filepath`\
指定したファイルをPCにコピーします。
- `adb bugreport dirname`\
バグレポートを発行してPC上の指定したディレクトリに保存します。
