# claude.md — reveal-pitch（営業プレゼン資料）

## 概要

メディア・コンフィデンス 12期の営業用プレゼン資料。Reveal.js（単一HTMLファイル）で構成。

- **公開URL**: https://hayanoryuki.github.io/ai-workflow-reveal/
- **GitHub**: https://github.com/HayanoRyuki/ai-workflow-reveal
- **HubSpotトラッキング**: Hub ID 21612534 を埋め込み済み
- **OGP**: ogp.png（1200×630）設定済み。シェア時にカバースライド画像が表示される

## ファイル構成

```
reveal-pitch/
├── CLAUDE.md          ← このファイル
├── index.html         ← プレゼン本体（Reveal.js 単一ファイル）
├── ogp.png            ← OGPシェア用画像（1200×630）
├── design-sample.pdf  ← デザインサンプル（参考用、gitignore対象）
└── images/            ← スライド用写真（png/jpg）
```

## スライド構成（全12枚）

| # | セクション | レイアウト | 内容 |
|---|-----------|-----------|------|
| 1 | カバー | 背景写真+グラデーション | タイトル、サブタイトル、会社名 |
| 2 | 提案資料メーカー | split（左コンテンツ+右写真） | scatter→converge レイアウト。4つのINPUTカードが収束してOUTPUTに |
| 3 | 提案資料メーカー | ヘッダー付き | デモ動画プレースホルダー（DEMO COMING SOON） |
| 4 | プロダクト一覧 | split | 2列×3行の商品カード（Lucideアイコン付き） |
| 5 | 技術基盤 | split | Claude × Temporal × MCP のアーキテクチャ図 |
| 6 | 他社比較（vs SaaS） | split | カード型比較行（✕/○の背景シンボル付き） |
| 7 | 他社比較（vs ChatGPT） | split | 同上 |
| 8 | セミナーメーカー | split | INPUT→OUTPUTのBA（Before-After）レイアウト |
| 9 | 導入パターン | split | A/B/Cの3パターンカード |
| 10 | 代表プロフィール | split | 写真（PHOTO プレースホルダー）+ 経歴テキスト |
| 11 | 料金・導入の流れ | split | 料金ボックス + 4ステップのシェブロンフロー |
| 12 | CTA + お問い合わせ | split（左CTA+右連絡先） | 左: お試し案内4ポイント、右: 連絡先パネル |

## デザインルール（厳守）

### 絶対NG
- **1辺だけ塗るボーダー禁止**。`border-top`, `border-left` 単独は使わない。必ず `border: 2px solid color` で4辺均等にする
- ヘッダーバーに会社名を入れない

### 基本方針
- **会社名はフッター**（左下、小さめ）: `.slide-footer` クラス
- **Lucideアイコン**を積極的に使う（CDN: unpkg.com/lucide@0.344.0）
- カードベースのデザイン。箇条書きのプレーンテキストは避ける
- 上揃え（`center: false`, `margin: 0`）
- splitレイアウト: 左コンテンツ + 右写真パネル（340〜400px）

### カラー
```css
--navy: #1a237e;      /* 見出し、強調 */
--blue: #4267f5;      /* メイン青 */
--blue-light: #7b9cf7; /* サブ青 */
--lavender: #e8eaf6;   /* ヘッダー背景 */
--ice-soft: #f0f7ff;   /* カード背景 */
```

### フォント
- Noto Sans JP（400/700/900）
- ベースサイズ: 26px

## 技術メモ

- Reveal.js 5.1.0（CDN）
- Lucide Icons 0.344.0（CDN）。`lucide.createIcons()` を `Reveal.initialize()` の後に呼ぶ
- Google Fonts: Noto Sans JP
- HubSpot Tracking: `//js.hs-scripts.com/21612534.js`
- GitHub Pages: mainブランチ / (root) からデプロイ

## 未完了・今後の作業

- [ ] スライド3: デモ動画ができたら差し替え（`<video data-autoplay src="demo.mp4">`）
- [ ] スライド10: プロフィール写真を差し替え（現在PHOTOプレースホルダー）
- [ ] design-sample.pdf は参考用。不要になったら削除可

## 更新履歴

- 2026-03-13: 初版作成（全12スライド）。GitHub Pages公開、OGP設定、HubSpotトラッキング埋め込み
