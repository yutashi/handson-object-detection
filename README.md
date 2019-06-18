# Hands on Object Detection

第30回isaax勉強会「ラズパイを使ってモノの判別をおこなってみよう」のサンプルリポジトリです。リモート参加枠の方は、あらかじめお手持ちのSDカードに必要なライブラリのインストールを行なってください。

## 環境

- Raspberry Pi 3 modelB/B+
- Raspbian (執筆時点では`2018-11-13-raspbian-stretch-lite.img`)

## Picameraの有効化

Picameraモジュールへのアクセスを有効かします。

```
sudo raspi-config nonint do_camera 0
```

再起動して設定を反映します。

```
sudo reboot
```

## TensorFlowのインストール

パッケージマネージャを更新し、依存ライブラリをインストールします。

```
sudo apt update && sudo apt upgrade
sudo apt install libatlas-base-dev libhdf5-serial-dev python3-pip
```

TensorFlowをインストールします。

```
sudo pip3 install tensorflow
```

`Remote end closed connection without response`エラーが表示される場合は、何度か実行を試すか`--timeout=0`オプションをインストール時に指定してください。

## OpenCVのインストール

前節同様、依存ライブラリからインストールします。

```
sudo apt install libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev
sudo apt install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt install libxvidcore-dev libx264-dev
sudo apt install qt4-dev-tools
sudo apt install libilmbase12 libopenexr22 libgstreamer1.0-dev
```

OpenCVをインストールします。

```
sudo pip3 install opencv-python
```

## サンプルコードの依存モジュール

最後に、サンプルコードの依存モジュールをインストールします。

```
sudo pip3 install flask imutils picamera[array]
```
