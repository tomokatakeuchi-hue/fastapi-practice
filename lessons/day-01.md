# Day 1: Python を動かす

## 今日のゴール

Python でテキストを表示し、変数と型の基本を知る。

---

## 1. Python が動くか確認する

ターミナルで以下を実行してください。

```bash
python3 --version
```

`Python 3.x.x` と出れば OK です。macOS には最初から入っています。

---

## 2. 最初のスクリプト

`practice/day-01/main.py` を作って、以下を書いてください。

### お題 1: 画面に表示する

PHP:
```php
<?php
echo "こんにちは";
```

Python:
```python
print("こんにちは")
```

**違い：** `<?php` も `;` も要りません。

---

### お題 2: 変数

PHP:
```php
$name = "田中";
$age = 30;
echo "$name は {$age} 歳です";
```

Python:
```python
name = "田中"
age = 30
print(f"{name} は {age} 歳です")
```

**違い：**
- `$` が要らない
- 文字列の先頭に `f` を付けると `{}` で変数を埋め込める（f-string）

---

### お題 3: 型を確認する

Python は型を書かなくても動きますが、確認はできます。

```python
name = "田中"
age = 30
price = 19.8
is_member = True

print(type(name))       # <class 'str'>
print(type(age))        # <class 'int'>
print(type(price))      # <class 'float'>
print(type(is_member))  # <class 'bool'>
```

PHP の `gettype()` と同じです。

---

### お題 4: 自分で書いてみる

`practice/day-01/main.py` に以下を書いて実行してください。

1. 自分の名前を変数 `name` に入れる
2. 好きな数字を変数 `lucky_number` に入れる
3. `「○○のラッキーナンバーは ○ です」` と表示する
4. 両方の型を表示する

```bash
python3 practice/day-01/main.py
```

---

## まとめ

| PHP | Python |
|---|---|
| `echo` | `print()` |
| `$name = "値";` | `name = "値"` |
| `"$name は {$age}"` | `f"{name} は {age}"` |
| `gettype($x)` | `type(x)` |
| `;` 必要 | 不要 |
| `<?php ... ?>` | 不要 |

明日は **リストと辞書**（PHP の配列に相当）をやります。
