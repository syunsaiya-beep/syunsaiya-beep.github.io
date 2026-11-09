# syunsaiya-beep.github.io（ユーザーPages / Digital Asset Links 用）

このリポジトリは、TWA（Trusted Web Activity）版「今晩何にする？」の
Digital Asset Links を配信するためのユーザーPagesリポジトリです。

## ファイル構成

- `.well-known/assetlinks.json` … TWA のリンク検証用（最重要）
- `index.html` … ルートにアクセスした人を `/konban-/` へ転送

## assetlinks.json の記入方法

1. Play Console でアプリを作成後、「設定 → アプリの完全性（App integrity）→
   アプリ署名鍵の証明書」に表示される **SHA-256 フィンガープリント**を取得。
2. `assetlinks.json` 内の `REPLACE_WITH_YOUR_SHA256_FINGERPRINT` を、
   その SHA-256（コロン区切り、大文字）に置き換える。
3. 変更をコミットして main ブランチへ push。

## 確認方法

公開後、次のURLが 200 で JSON を返すことを確認する:

```
https://syunsaiya-beep.github.io/.well-known/assetlinks.json
```

（`/konban-/` 配下ではなく、ドメイン直下に置くのが必須です）
