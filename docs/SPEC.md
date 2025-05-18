# 仕様書｜iOS Calculator Clone

## 1. アプリ名（仮）
- iOS Calculator Clone
- スマートフォン対応レスポンシブ電卓アプリ

---

## 2. 主な機能

| 機能名 | 説明 |
|--------|------|
| 四則演算 | 足し算・引き算・掛け算・割り算が可能 |
| 画面表示 | 入力中の数値や式がリアルタイムに表示される |
| AC機能 | 表示をリセットし、0に戻す |
| = ボタン | 入力された式を計算し、結果を表示 |
| 入力補完 | 先頭の0を自動で上書き、演算子は文字列に追加される |

---

## 3. UI設計（レイアウト）

- スマホ画面を想定した画面幅：最大400px
- ボタンは4列のグリッド表示、1行あたり4個配置
- 正円のボタン（`border-radius: 50%`）を採用
- 色分けによる分類：
  - 灰色：機能ボタン（AC等）
  - 黒：数字ボタン
  - オレンジ：演算子

---

## 4. 使用技術

- HTML5（構造）
- CSS3（グリッド、メディアクエリ、色と角丸など）
- JavaScript（イベント処理、DOM操作、`eval()` による式評価）

---

## 5. 開発環境

| 項目 | 内容 |
|------|------|
| エディタ | Cursor / VS Code |
| 確認端末 | iPhone 16 / MacBook |
| 公開環境 | Vercel |
| 使用フォント | `-apple-system`（San Francisco 系） |

---

## 6. フォルダ構成（例）

```
ios-style-calculator/
├── docs/
│   ├── images/              ← 文書に使用する画像フォルダ
│   ├── PROCESS_LOG.md       ← 実装記録・学びの流れ
│   ├── SPEC.md              ← 機能仕様・設計意図
│   └── STUDY_MEMO.md        ← コードの理解や調査のメモ
├── index.html               ← アプリの本体
├── style.css               ←
├── script.js
└── README.md 

```

---

## 7. 今後の拡張予定

- パーセント計算
- クリア（C）機能とAC切り替え
- 計算履歴の保存・表示
- 科学計算（平方根、指数、三角関数など）

---

## 8. 機能と関連コード・学習ポイント

| 機能 | 使用コード・構文 | 学んだこと・ポイント |
|------|------------------|------------------------|
| 数字・記号の表示 | `addEventListener('click', ...)`<br>`display.textContent += buttonText` | イベント処理の基礎、表示更新 |
| 四則演算 | `.replace('×', '*')`<br>`eval()` | 記号変換、式の評価 |
| 0の上書き処理 | `if (display.textContent === '0') { ... }` | 条件分岐の使い方 |
| AC機能 | `if (buttonText === 'AC') { display.textContent = '0'; return; }` | 処理の中断（`return`） |
| クラス指定 | `querySelectorAll('.number-button, .operator-button')` | 複数要素の取得方法 |
| レスポンシブ対応 | `@media`, `vw`, `vh` | 画面サイズに応じたUI調整 |
| フォント指定 | `font-family: -apple-system` | San Francisco フォントの適用 |
| ボタン見た目 | `border-radius: 50%`, `aspect-ratio: 1 / 1` | UIを整えるCSS指定 |

---

## 最終更新
2025/05/18
