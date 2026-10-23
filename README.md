# Phrase Ring

シチュエーション別の英語フレーズ集（PWA / GitHub Pages）

## 構成

| ファイル | 役割 |
|---|---|
| `index.html` | アプリ本体 |
| `phrases.json` | フレーズデータ（追加は基本的にここだけ） |
| `sw.js` | オフライン対応（Service Worker） |
| `manifest.webmanifest`, `icons/` | ホーム画面追加用 |

## データ形式

```json
{
  "situations": [
    {
      "id": "self-intro",
      "name": "自己紹介・雑談",
      "topics": [
        {
          "id": "study",
          "name": "学業・研究",
          "phrases": [
            { "en": "英文", "ja": "和訳", "key": "強調する表現（任意）", "note": "メモ（任意）" }
          ]
        }
      ]
    }
  ]
}
```

- 1カード = 1つの内容。英文は8〜15語を目安にする
- `key` は英文中の一致部分がハイライトされる

## 機能

- シチュエーション切替・検索（英語・日本語）
- 表示モード：両方 / 英→日（和訳を隠す） / 日→英（英語を隠す）。カードをタップすると表示される
- ライト / ダークモード自動切替、オフライン対応

## 公開

Settings → Pages → Branch: `main` / `/ (root)`

## 更新時の注意

`index.html` や `sw.js` を変更したら、`sw.js` の `CACHE` のバージョンを上げる（`phrases.json` だけの変更なら不要）。
