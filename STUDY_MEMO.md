# Markdownファイル名の大文字と小文字の使い分けについて(2025/05/15)


## 概要
Markdownファイル名において、大文字と小文字には技術的な差はないが、視認性や分類の目的で使い分けがされる。

---

## 大文字を使う理由

### 1. 視認性の向上
- 大文字のファイル名はファイルツリーで目立つ。
- 文書ファイルをすぐに識別できる。

### 2. 役割の明示
以下のように用途別に区別されることが多い：

| ファイル名         | 用途                     |
|------------------|--------------------------|
| README.md        | リポジトリの概要・導入文書   |
| PROCESS_LOG.md   | 開発や学習の進捗記録        |
| TECH_SPEC.md     | 技術仕様書                 |
| TODO.md          | タスクリスト               |

### 3. コードファイルとの区別
- コード：小文字（例：`main.js`, `index.html`）
- 文書：大文字（例：`README.md`, `LOG.md`）

---

## 推奨ルール（例）

- 文書系 `.md` ファイル：**大文字**で始める
- コードファイル：**小文字**で統一

※チームや個人でルールを明示しておくと混乱を避けやすい

---

## 備考
- `.MD`（拡張子全て大文字）も動作するが、`.md` が一般的
- GitHubなどの一部ツールは `README.md` を特別扱いする（トップに自動表示）

# 📚 San FranciscoフォントをCSSで使いたいときの注意メモ

## ❓ San Franciscoってなに？(2025/05/15)

- Appleが作った**iPhoneやMacの標準フォント**
- iPhoneの時計アプリ・メッセージアプリなど、AppleのほぼすべてのUIで使われている
- スタイリッシュで読みやすく、Appleらしさが出る！

---

## ❓ CSSでこう書きたくなるけど…

```css
font-family: 'San Francisco', sans-serif;
```

⬆️ これは **使えない！動かない！** 😢

---

## ❗ なぜ `'San Francisco'` と書いても動かないの？

- **Appleはこのフォントに“名前”をつけていない**（びっくりだけど事実）
- インストールされてるフォントじゃなくて、**システムの中に隠れてる特別なフォント**
- WindowsやAndroidには当然入ってない
- Appleの中でも「San Francisco」という**名前では指定できないようにしてある**

---

## ✅ じゃあどうすればいいの？

Appleが用意してくれてる“魔法のキーワード”を使う！

```css
font-family: -apple-system;
```

これを書くだけで：

- iPhone → San Francisco になる✨
- Mac → San Francisco になる✨
- WindowsやAndroidでは → 近いフォントが代わりに使われる

---

## ✅ 実際によく使われてるおすすめの書き方

```css
font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
```

| フォント名              | 説明                                        |
|-------------------------|---------------------------------------------|
| `-apple-system`         | Apple公式のSan Francisco指定用キーワード   |
| `BlinkMacSystemFont`    | Chrome/macOSで使われるSan Francisco対応     |
| `"Helvetica Neue"`      | 旧iOSで使われてたスタイリッシュな代替文字   |
| `sans-serif`            | 最後の保険（どの環境でもゴシック体になる） |

---

## ✨ 覚えておくべきまとめ

- `'San Francisco'` はCSSで**書いても効かない**
- Apple風にしたいときは **`-apple-system` を使おう**
- 複数フォントを並べることで、**いろんな環境でも見た目が安定する**

---

## 💡 具体例（CSSで使うとき）

```css
body {
  font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
}
```

---

## 🔚 つまり…

> 📱 **iPhoneの電卓っぽくしたい！**  
> 💻 **AppleっぽいUIにしたい！**

そんなときは、  
→ `'San Francisco'` じゃなくて `-apple-system` を使うこと！


