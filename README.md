# ランルート（RUN ROUTE）

距離・往復/片道・起伏（フラット／おまかせ／坂多め）を選ぶだけで、ランニングコースを自動で作るWebアプリです。

## 中身

| ファイル | 役割 |
|---|---|
| index.html | アプリ本体 |
| manifest.webmanifest | ホーム画面に追加したときの名前・アイコン・色 |
| sw.js | アプリ本体をキャッシュして起動を速くする |
| icons/ | アプリアイコン（32 / 180 / 192 / 512 / 1024px、Android用マスカブル） |

## GitHub Pages への公開手順

1. GitHub で新しいリポジトリを作る（例：`runroute`、Public）。
2. 「Add file」→「Upload files」で、このフォルダの中身をすべてアップロードする。
   `icons` フォルダごとドラッグし、index.html がリポジトリの一番上にある状態にする。
3. 「Commit changes」を押す。
4. 「Settings」→「Pages」→ Source を「Deploy from a branch」、Branch を `main` / `/(root)` にして Save。
5. 1〜2分後に `https://<ユーザー名>.github.io/runroute/` で開けるようになる。

## iPhone のホーム画面に追加

1. Safari で公開URLを開く。
2. 共有ボタン →「ホーム画面に追加」。
3. 初回起動時に位置情報の許可を求められるので「許可」を選ぶ。

## 更新するとき

index.html を差し替えたら、sw.js の 1 行目付近の `runroute-v1` を `runroute-v2` のように番号を上げてからアップロードしてください。古いキャッシュが残らず、新しい版がすぐ反映されます。

## 使っている外部サービス

- 地図：OpenStreetMap タイル
- 経路検索：routing.openstreetmap.de（FOSSGIS、徒歩プロファイル）
- 標高：Open-Meteo Elevation API（Copernicus DEM）
- 地名検索：Nominatim

いずれも無料の公開サーバーで、個人利用の範囲を想定しています。販売などで利用者が増える場合は、APIキー制のサービス（OpenRouteService など）への切り替えを検討してください。
