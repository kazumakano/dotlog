---
title:       "Pythonの既定バージョンを設定する方法"
subtitle:    ""
description: "アプリ実行エイリアスを編集"
date:        2021-11-12
author:      "Kazuma Kano"
image:       true
tags:        [windows]
categories:  [trouble]
published:   true
---

WindowsのPython実行環境について、私は複数バージョンのPythonをMicrosoft Storeから直接インストールしています。
その場合、`python3.9`や`pip3.10`のようにバージョンを直接指定して実行することはできますが、毎回バージョンを指定するのは面倒です。
今回は、ただの`python`コマンドや`pip`コマンドで呼ばれるバージョンを設定する方法についてまとめます。

まず、設定 > アプリ > アプリと機能 > アプリ実行エイリアス を選択します。
ここでは、各アプリを実行するためのコマンドのエイリアスを設定できます。
例えば、python3.9というアプリに対してpython.exeというエイリアスを設定すれば、`python`コマンドでpython3.9が呼ばれるようになります。
