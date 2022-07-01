# Jobs And Instances

データ取得が可能なエンドポイントは instanceとよび、多くの場合はひとつのプロセスがそうよばれる。同一の目的で収集される場合は jobとよばれる。

たとえばこんな感じ。

- job: `api-server`
  - instance 1: `1.2.3.4:5670`
  - instance 2: `1.2.3.4:5671`
  - instance 3: `5.6.7.8:5670`
  - instance 4: `5.6.7.8:5671`

## Automatically generated labels and time series

targetを取得するとき、それらを識別するために自動で labelが付与される。

- `job` : targetに属する jobの名称
- `instance` : targetの URLとなる `<host>:<port>`

収集したデータにすでにそのラベルが入っていた場合、 `honor_labels` の設定に従って動作する。  
他にもデフォルトで保存する時系列データがあるもよう。

- `up{job="<job-name>", instance="<instance-id>"}` : instanceが生きていると判断できたら (アクセスできるとか) `1` になり、そうでなければ `0` になる
- etc.
