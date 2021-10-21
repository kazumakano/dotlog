---
title:       "PowerShellの起動時にメッセージを表示させない方法"
subtitle:    ""
description: "NoLogoパラメータを指定"
date:        2021-10-22
author:      "Kazuma Kano"
image:       true
tags:        [windows]
categories:  []
published:   true
---

最近ようやくPowerShellをバージョン7にアップデートしたのですが、デフォルトでは起動時に以下のようなコピーライトとヘルプのメッセージが表示されます。
```cmd
PowerShell 7.1.5
Copyright (c) Microsoft Corporation.

https://aka.ms/powershell
Type 'help' to get help.
```
毎回表示されると結構気になります。今回はこのメッセージを表示させない方法について調べたのでまとめます。

# Parameter
PowerShellには起動時に指定できるパラメータがいくつか用意されています。
`-NoLogo`パラメータはそのうちの1つです。
このパラメータを指定するとコピーライトやヘルプのメッセージを省略できます。

パラメータは以下のようにpowershellの起動コマンドの後ろに付けることで指定できます。
```cmd
powershell -Parameter
```

その他のパラメータについてはこちらの[ドキュメント](https://docs.microsoft.com/ja-jp/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1)を参照してください。

# How to Set
私は普段Windows Terminal上でPowerShellを使っています。
この場合、Windows TerminalからPowerShellを呼び出すコマンドにパラメータを設定してやる必要があります。
具体的には、Windows Terminal > 設定 > PowerShell > 全般 > コマンドライン の欄にあるコマンドに`-NoLogo`を付け足すことで設定できます。
これでWindows Terminal上でPowerShellを起動したときにメッセージが表示されないようになりました。

上記の設定はWindows Terminalに対するものなので、ショートカットアイコンから直接起動した際にはメッセージは表示されたままです。
これを表示させないようにするにはショートカットからPowerShellを呼び出すコマンドにパラメータを設定してやる必要があります。
具体的には、スタート > PowerShell > ファイルの場所を開く > Powershell > プロパティ > リンク先 の欄にあるコマンドに`-NoLogo`を付け足すことで設定できます。