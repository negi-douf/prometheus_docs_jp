# Overview

## Prometheusとは？

Prometheusはオープンソースの監視・アラートツール。元は SoundCloudによって 2012年に開発された。それが 2016年に Cloud Native Foundationのプロジェクトに加入した。  
Prometheusは時系列データをラベルとよばれる Key-valueデータとともに保存する。  

## 機能

- 時系列データを多次元にできる
- PromQLというクエリ言語で時系列データを処理する
- 基本は HTTPによる pullモデルでデータを収集する
- pushモデルは仲介のゲートウェイを通してのみサポート
- 監視対象は service discoveryと事前の定義をサポート

## メトリクスとは？

レイパーソンによると、メトリクスは数値的な観測。アプリケーションによって観測したい情報は異なる。

## 構成要素

Prometheusは複数の要素からなるが、その多くはオプション。

- Prometheus server  
メインコンポーネントで、時系列データを収集・保存する。
- client libraries  
アプリケーションのデータの計測をおこなう？
- push gateway  
push型のメトリクスを蓄える？Prometheus serverが読みにくる。
- exporter  
監視対象の情報を持つもの。Prometheus serverが読みにくる。
- alertmanager  
アラートの処理を担う。

デフォルトで可視化の仕組みもあるが、Grafanaなんかを使うこともできる。

## どのようなケースで使う？

純粋に時系列の数値データを収集したいときに適している。また、マイクロサービスで動的に構成が変化するときや可用性を高めたいときなどにも。
