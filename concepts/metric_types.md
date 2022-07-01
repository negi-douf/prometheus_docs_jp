# Metric Types

Prometheus client libraryは 4つのメトリックタイプを提供する。現状 Prometheusサーバは型情報を識別・利用していない。これは将来変更される可能性がある。

## Counter

counterはゼロから順に増えていくというシンプルな情報。ゼロにリセットするか増やすかのみ。

## Gauge

gaugeは上昇と下降のあるデータを表現するメトリック。温度やメモリ使用率などに使える。

## Histogram

counterを複数まとめたようなもの？

## Summary

histogramと似たようなもの。集計結果を特定の時間に絞って計算できるっぽい。
