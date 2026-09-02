# dachaclub-media

`@dachaclubdayo` の Instagram 投稿用・**画像置き場**。

Instagram の Content Publishing API は、画像を**公開URLでホスト**していないと投稿できない
（Meta のサーバーが画像を取りに来るため）。**Googleドライブのリンクは使えない**（HTMLを返すため）。
そのための公開リポジトリ。

---

## 2つの役割

| 用途 | 場所 |
|---|---|
| 画像のホスティング | `posts/` |
| OAuth のリダイレクト先 | `index.html`（GitHub Pages） |

---

## 画像の追加

1. **JPEG** を用意する（1080×1350 推奨）
   - PNG・HEIC は Instagram が受け付けない
   - 変換は `インスタ運用/scripts/prepare_photos.py` が行う
2. `posts/` に置く
3. commit して push する
4. 次のURLで参照できる

```
https://raw.githubusercontent.com/Arashimaww/dachaclub-media/main/posts/<ファイル名>.jpg
```

---

## ⚠️ 置く前に確認すること

**このリポジトリは公開されている。** 置いた画像は誰でも見られる。

- **Instagram に投稿する画像だけ**を置く。作業用の写真を置かない
- **顔がはっきり写った人物写真は、本人の許可が取れたものだけ**
- ファイル名に `（顔未）` が付いた素材は**使わない**
- 個人情報が写り込んでいないか確認する（表札・車のナンバー・書類など）

---

## GitHub Pages

`index.html` が `https://arashimaww.github.io/dachaclub-media/` で公開される。
Meta のアプリ設定で **OAuth リダイレクトURI** としてこのURLを登録する。

`localhost` は Meta の管理画面で保存できないため、実在する HTTPS の URL が必要。

---

## 秘密情報は置かない

アクセストークン・App Secret・`credentials.json` は**絶対にここに置かない。**
持っている人が誰でも投稿できる鍵になる。
