# Network Visualizer

これは、D3.jsを使ってグラフを可視化するツールです。`index.html`をブラウザで開くと(グラフ理論で言うところの)グラフが表示されます。折れ線グラフや棒グラフというときの「グラフ」と紛らわしいので、以降「ネットワーク」と呼ぶことにします。

# 使い方
## 開けるファイル形式

jsonファイルとcsvファイルを開くことができます。拡張子はそれぞれ`.json`, `.csv`でなければならず、それ以外の拡張子は読み込めません。

### jsonファイル

次のようなjsonファイルを読み込みます。

```json
{
    "nodes": [
        { "id": "ノード1", "name": "Node 1", "group": 1, "explain": "This is node 1" },
        { "id": "ノード2", "name": "Node 2", "group": 2, "explain": "This is node 2" },
        { "id": "ノード3", "name": "Node 3", "group": 2, "explain": "This is node 3" }
    ],
    "links": [
        { "source": "ノード1", "target": "ノード2", "value": 2 },
        { "source": "ノード2", "target": "ノード3", "value": 1 }
    ]
}
```

`id`, `source`, `target`以外は任意項目です。

- `name`は、ノードの脇に表示される文字列を指定します。存在しない場合は`id`が表示されます。
- `group`は、ノードの色分けをすることができます。
- `explain`は、ノードのツールチップを追加します。
- `value`は、エッジのツールチップを追加します。

### csvファイル

次のようなcsvファイルを読み込みます。

```csv
source,target,value
ノード1,ノード2,2
ノード2,ノード3,1
```

`value`は任意項目です。`name`, `group`, `explain`は指定できません。

