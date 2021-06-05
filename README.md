# FerenOSインストールメモ
## はじめに

普段Ubuntuを使っていて、より良いLinuxを求めて調べていました。

比較的最近出てきて、使いやすそうなFerenOSに注目して、試してみました。



## 使いやすそうなポイント
 - 直感的なファイル操作
 - わかりやすいNotifications
 - [Steam](https://feren-os-user-guide.readthedocs.io/en/latest/steam.html)も使える


## 環境, 周辺機器
 - PC (Ubuntu)
 - PC (FerenOSインストール用)
 - USBメモリー
 - Wifi環境(有線ネットワークが提供されていない環境)の場合
     - スイッチングハブ
     - LANケーブル (2本)

## インストール用USB作成
 - [ISOをダウンロード](https://ferenos.weebly.com/get-feren-os.html)
 - [balenaEtcher](https://www.balena.io/etcher/)をダウンロード
 - [USBにISOを書き込む](https://feren-os-user-guide.readthedocs.io/en/latest/writetousb.html)


## インストール
今回はデュアルブートする設定で進めます。

 - PCのパーティショニング
     - Windows:[Create and format a hard disk partition](https://support.microsoft.com/en-us/windows/create-and-format-a-hard-disk-partition-bbb8e185-1bda-ecd1-3465-c9728f7d7d2e)
     - Mac:[Partition a physical disk in Disk Utility on Mac](https://support.apple.com/guide/disk-utility/partition-a-physical-disk-dskutl14027/mac)
 - PCにUSBメモリーを挿入して起動し、「Replace a partition」の設定でインストール
     - Windows:[Installing Feren OS alongside Windows](https://feren-os-user-guide.readthedocs.io/en/latest/installwithwindows.html)
     - Mac:[Installing Feren OS alongside macOS](https://feren-os-user-guide.readthedocs.io/en/latest/installwithmacos.html)


## ネットワーク環境
有線ネットワークが提供されている環境では、デバイスドライバのインストールのみで完了です。

Wifi環境(有線ネットワークが提供されていない環境)の場合、スイッチングハブの準備から順に進めていきます。

今回は有線LANを構築し、FerenOS側からインターネットに接続できるようにします。


## スイッチングハブの準備
 - スイッチングハブとPC(２台)をLANケーブルで接続します

## Ubuntu側の設定
 - 無線接続をWAN, 有線接続をLANとして設定します
     - 参考:[How to build Linux Router with Ubuntu Server 20.04 LTS](https://www.networkreverse.com/2020/06/how-to-build-linux-router-with-ubuntu.html)
     - netplan設定ファイル:[01-network-manager-all.yaml](https://github.com/ani-amou/memo-for-feren-os-install/blob/master/01-network-manager-all.yaml)

## FerenOS側の設定
 - Manualで有線接続を設定します
![Manualで有線接続を設定](/img/wire_connection_setting02.jpg?raw=true "Wired Connection Setting")

## デバイスドライバのインストール
 - USBメモリーを挿入します
 - Driver Managerを起動し、必要なデバイスドライバをインストールします
     - 参考:[Driver Manager](https://feren-os-user-guide.readthedocs.io/en/latest/drivermanager.html)

## おわりに
Wifiのみの環境では、Ubuntuのインストールに比べるとかなり大変でした。

今のところ、使いやすさは良い印象です。

アップデートに期待しつつ使っていきます。
