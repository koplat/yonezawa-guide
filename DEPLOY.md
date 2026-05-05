# GitHub Pages 公開手順

ローカル → GitHub → GitHub Pages → LINE/Slackでサムネイル付きシェア、までの全手順です。

---

## 1. リポジトリを作成

1. https://github.com/new にアクセス
2. **Repository name**：`yonezawa-guide`
3. **Public** を選択（GitHub Pagesは無料アカウントでもPublicなら使えます）
4. **Add a README file** にチェックを入れない（ローカルで作成済み）
5. **Create repository** をクリック

---

## 2. ファイルをアップロード

新しい空のRepoが開いたら、画面上部の **「uploading an existing file」** リンクをクリックします。

ローカルの `yonezawa-guide/` フォルダ内のファイルを **すべてドラッグ&ドロップ** します（フォルダごとドラッグでもOK）。

アップロードされる構造：

```
README.md
DEPLOY.md
index.html
og-cover.png
uesugi-jinja/
  ├── index.html
  └── og-image.png
yonezawa-ori/
  ├── index.html
  └── og-image.png
```

下部の **Commit changes** ボタンをクリックしてコミットします。

---

## 3. GitHub Pagesを有効化

1. Repoページの **Settings**（歯車アイコン）をクリック
2. 左サイドバーで **Pages** を選択
3. **Source** で **Deploy from a branch** を選択
4. **Branch** で **main** を選び、フォルダは **/ (root)** のまま
5. **Save** をクリック

数十秒〜数分後、ページ上部に
```
Your site is live at https://koplat.github.io/yonezawa-guide/
```
と表示されたら公開完了です。

---

## 4. 動作確認

ブラウザで以下のURLにアクセスして動作を確認してください。

| URL | 内容 |
|-----|------|
| https://koplat.github.io/yonezawa-guide/ | ランディングページ（両ガイドへのリンク） |
| https://koplat.github.io/yonezawa-guide/uesugi-jinja/ | 上杉神社ガイド |
| https://koplat.github.io/yonezawa-guide/yonezawa-ori/ | 米沢織ガイド |

各ガイドで以下を確認：
- 言語タブ（🇯🇵 / 🇬🇧 / 🇹🇼）の切替が動作する
- モードタブ（🎌 観光客 / 📚 通訳者）の切替が動作する
- 文字化けがない

---

## 5. OGP（LINEプレビュー画像）の動作確認

各URLを **LINE** でトーク画面に貼り付けて、サムネイル画像・タイトル・説明文が正しく表示されることを確認します。

### キャッシュ更新が必要な場合

LINEはOGPプレビューを比較的長くキャッシュします。OGP画像を変更した場合や、初回表示が乱れる場合は以下のいずれかを試してください。

- URLにクエリパラメータを追加して再共有：`https://koplat.github.io/yonezawa-guide/uesugi-jinja/?v=2`
- Facebook Sharing Debugger でクロールを強制：https://developers.facebook.com/tools/debug/
- Twitter Card Validator で画像確認：https://cards-dev.twitter.com/validator

### 検証ツール

| ツール | URL |
|--------|-----|
| OGPチェック（一般） | https://www.opengraph.xyz/ |
| OGP（メタタグ確認） | https://metatags.io/ |
| LINEプレビュー（参考） | LINE公式は専用デバッガなし。実際にLINEに貼って確認 |

---

## 6. 更新の手順

ガイド内容を修正する場合：

1. ローカルで `index.html` を編集
2. GitHub Repoの該当ファイルを編集（または再アップロード）
3. Commitすると数分後に自動的にPagesに反映

---

## トラブルシューティング

### Q. Pagesが有効化されない / 404になる
- Settings → Pages の設定を再確認
- Branch が `main`、Folder が `/ (root)` になっているか確認
- 数分待っても反映されない場合は Actions タブでビルドログを確認

### Q. OGP画像が表示されない
- 画像URLが絶対URL（`https://...`）になっているか確認
- 画像ファイル（og-image.png）が正しいパスにアップロードされているか確認
- ブラウザでOGP画像URLを直接開いて、画像が表示されるか確認

### Q. LINEで以前のサムネイルが残る
- URLに `?v=2` などクエリパラメータを付与して再共有
- LINEは数日キャッシュを持つことがあるため、しばらく待つ

---

## 補足：独自ドメインに設定する場合

Settings → Pages の **Custom domain** に `guide.example.com` を設定し、DNSにCNAMEレコードを追加することで、独自ドメイン公開も可能です。HTTPSは自動取得されます（数分〜数十分）。
