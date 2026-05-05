# 羽前米沢 多言語ガイド｜Yonezawa Multilingual Guides

山形県米沢市の文化資源を、日本語・English・繁體中文の3言語 × 観光客向け／通訳者向けの2モードで解説する多言語ガイド集です。

**公開URL**：https://koplat.github.io/yonezawa-guide/

## 収録ガイド

| Guide | URL | テーマ |
|-------|-----|--------|
| 01 上杉神社 | `/uesugi-jinja/` | 米沢城本丸跡の上杉神社・松岬神社・春日神社・福徳稲荷神社 |
| 02 米沢織  | `/yonezawa-ori/` | 200年以上の織物の町・米沢織の歴史と工程、紅花染、NHK World番組 |

## 構成

- **3言語**：🇯🇵 日本語 / 🇬🇧 English / 🇹🇼 繁體中文
- **2モード**：🎌 観光客向け（Tourist） / 📚 通訳者向け（Interpreter / Study Mode）
- 通訳者モードには「⚠️ ファクトチェック注意点」を併記し、一次史料未確認の伝承と検証可能な事実を区別

## ファイル構成

```
yonezawa-guide/
├── index.html              # ランディングページ
├── og-cover.png            # ランディング用OGPカバー画像
├── README.md               # このファイル
├── uesugi-jinja/
│   ├── index.html          # 上杉神社ガイド（OGP対応）
│   └── og-image.png        # 上杉神社用OGP画像
└── yonezawa-ori/
    ├── index.html          # 米沢織ガイド（OGP対応）
    └── og-image.png        # 米沢織用OGP画像
```

## デプロイ

GitHub Pagesで公開しています。ブランチ `main` のルートを公開対象とする設定です。

詳細手順は `DEPLOY.md` を参照してください。

## 出典・参考

- [上杉神社 御由緒](https://uesugi-jinja.or.jp/history/)
- [米沢繊維協議会「米沢織物とは」](https://www.yoneori.com/what/)
- [NHK World "YONEZAWA: Beni, Japanese Red"](https://www3.nhk.or.jp/nhkworld/en/shows/6053013/)
- [経産省東北「米沢織」地域団体商標](https://www.tohoku.meti.go.jp/chizai-enet/support/brand/yonezawaori.html)

## ライセンス

本リポジトリの著作物は、観光ガイド・通訳ガイド・旅行業者の現場使用を主目的とする多言語解説資料です。一次資料の引用・参考元情報の著作権は各原典に帰属します。

Compiled May 2026.
