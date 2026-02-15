# pokeca-list-jpn

## 使い方 (Usage)

### カードデータの更新・作成

遊々亭の販売ページからカード情報を取得し、JSONファイルを更新または作成するスクリプトです。

#### インタラクティブモード（推奨）

引数を指定せずに実行すると、対話モードが起動します。
遊々亭のパック一覧から更新したいパックを選択するだけで、自動的にJSONファイルを更新・作成できます。

```bash
python3 script/update_from_yuyutei.py
```

実行後、キーワード検索などで対象のパックを探し、番号を選択してください。

#### コマンドラインモード（上級者向け）
URLや保存先を直接指定したい場合は、引数を使用します。

```bash
python3 script/update_from_yuyutei.py [遊々亭のURL] [JSONファイルのパス]
```

例：M3パックのデータを更新する場合
```bash
python3 script/update_from_yuyutei.py "https://yuyu-tei.jp/sell/poc/s/m03" packs/M/M3.json
```

#### 新規パックの作成

新しいJSONファイルを作成する場合は、`--pack-id` オプションでパックIDを指定してください。

```bash
python3 script/update_from_yuyutei.py [遊々亭のURL] [新規JSONファイルのパス] --pack-id [パックID]
```

例：SV11Bパックを新規作成する場合
```bash
python3 script/update_from_yuyutei.py "https://yuyu-tei.jp/sell/poc/s/sv11b" packs/SV/SV11B.json --pack-id SV11B
```

### 注意点
- 既存のカードデータに `pokemon-card.com` の画像URLが含まれている場合、それは維持されます。
- 新規追加されるカードには、遊々亭の画像URLが使用されます。