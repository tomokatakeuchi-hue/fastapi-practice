# FastAPI 30日コーディング練習ロードマップ

PHP + WordPress 経験者が、Python の基礎から FastAPI で API を作り、Next.js とつなげるまでの 30 日間プランです。

DB は **SQLite**（ファイル1つ、インストール不要）を使います。

毎日1つ「お題」が出されるので、`practice/day-XX/` に自分でコードを書いて挑戦します。

---

## Week 1: Python の基本（PHP との違いだけ覚える）

| Day | テーマ | PHP との対応 |
|---|---|---|
| 1 | Python を動かす（print, 変数, 型） | `echo`, `$var` |
| 2 | リストと辞書（配列の代わり） | `array()`, 連想配列 |
| 3 | if / for / while | ほぼ同じ。`{}` → インデント |
| 4 | 関数を作る | `function` → `def` |
| 5 | クラスの基本（最低限だけ） | `class`, `$this` → `self` |
| 6 | ファイルの読み書き + JSON | `file_get_contents`, `json_decode` |
| 7 | 型ヒント（FastAPI で必須になる） | PHP 7 の型宣言と似ている |

## Week 2: FastAPI の基本（API を作る）

| Day | テーマ | WordPress との対応 |
|---|---|---|
| 8 | Hello FastAPI — 最初の API | `register_rest_route` で GET を作るのと同じ |
| 9 | パスパラメータ（`/users/123`） | WP の `(?P<id>\d+)` |
| 10 | クエリパラメータ（`?page=2&limit=10`） | `$_GET` |
| 11 | POST でデータを受け取る（Pydantic） | `$_POST` + バリデーション |
| 12 | レスポンスの形を決める | `wp_send_json()` |
| 13 | Swagger UI（`/docs`）を使いこなす | Postman / REST API テスト画面 |
| 14 | メモアプリ API（メモリ上で CRUD） | DB なしで4操作を全部作る |

## Week 3: データベース（SQLite + SQLAlchemy）

| Day | テーマ | PHP + MySQL との対応 |
|---|---|---|
| 15 | SQLite でテーブルを作る（Python 標準） | `CREATE TABLE` |
| 16 | SQLAlchemy でモデル定義 | テーブル定義を Python クラスで書く |
| 17 | Create — データを保存する | `INSERT INTO` |
| 18 | Read — データを取得する | `SELECT ... WHERE` |
| 19 | Update + Delete — 更新と削除 | `UPDATE`, `DELETE` |
| 20 | Alembic でマイグレーション | `wp dbDelta()` / `ALTER TABLE` |
| 21 | リレーション（1対多） | `JOIN` |

## Week 4: 実践（Next.js とつなぐ）

| Day | テーマ | 説明 |
|---|---|---|
| 22 | エラーハンドリング | 404, 422, 500 の返し方 |
| 23 | ファイル分割（router / schemas / models） | 大きくなったコードを整理する |
| 24 | CORS 設定 | Next.js（:3000）→ FastAPI（:8000）を許可する |
| 25 | Next.js から GET する | `fetch()` でデータ取得 → 画面表示 |
| 26 | Next.js から POST する | フォーム送信 → FastAPI → DB 保存 |
| 27 | Next.js で CRUD 全部動かす | 一覧・追加・編集・削除 |
| 28 | 認証の基本（トークン） | ログイン → JWT トークン発行 |
| 29 | 総合演習（小さなアプリ作り） | ここまでの全部を使う |
| 30 | 振り返り + 次のステップ | デプロイ、本番 DB への切り替え |

---

## セットアップ

```bash
cd /Users/tomokatakeuchi/project/fastapi-practice
python3 -m venv .venv
source .venv/bin/activate
pip install fastapi uvicorn sqlalchemy alembic
```

## 進め方

1. `lessons/day-XX.md` を読む
2. 指示に従って `practice/day-XX/` にコードを書く
3. ターミナルで実行して動作確認する
4. 完了したら次の Day へ

## 実行方法

```bash
# Python スクリプト（Week 1）
python practice/day-01/main.py

# FastAPI サーバー（Week 2 以降）
uvicorn practice.day-08.main:app --reload
# → http://localhost:8000/docs でブラウザから確認
```
