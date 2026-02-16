# エンジニア向け職務経歴書テンプレート

このディレクトリには、エンジニア向けの職務経歴書テンプレートと印刷用CSSが含まれています。

## ファイル構成

- `resume_template.md` - 職務経歴書のMarkdownテンプレート
- `resume_print.css` - 印刷用CSS（HTML/PDF変換時に使用）
- `README.md` - このファイル

## 使い方

### 1. テンプレートの編集

`resume_template.md` を開いて、あなたの情報に書き換えてください。

### 2. HTMLへの変換

Markdownエディタの多くは、HTMLプレビュー機能を持っています。以下のいずれかの方法でHTMLに変換できます：

#### 方法A: pandocを使用（推奨）

```bash
# pandocのインストール（macOS）
brew install pandoc

# HTML変換（CSSを埋め込み）
pandoc resume_template.md -o resume.html --self-contained -c resume_print.css --metadata title="職務経歴書"
```

#### 方法B: Markdownエディタを使用

VS Code、Typora、MacDownなどのエディタで、Markdownファイルを開き、HTMLとしてエクスポートします。その際、`<head>`タグ内に以下を追加してください：

```html
<link rel="stylesheet" href="resume_print.css">
```

### 3. PDFへの変換

HTMLが作成できたら、ブラウザで開いて印刷機能（Cmd+P）から「PDFとして保存」を選択します。

**印刷設定のポイント：**
- 用紙サイズ: A4
- 余白: デフォルト（またはカスタムで上下左右15mm）
- 背景のグラフィック: オン（色付きセクションを表示するため）

## テンプレートの特徴

### 1. 技術スタックの視覚化
- タグ形式で技術を列挙
- カテゴリ別に整理（言語、フレームワーク、インフラなど）
- 一目でスキルセットが把握できるレイアウト

### 2. 実績重視の構成
- 具体的な数値を記載（例：「レスポンス速度を60%改善」）
- 技術的な課題解決を明記
- ビジネスインパクトを強調

### 3. 印刷最適化
- A4サイズに最適化
- 改ページ制御により読みやすいレイアウト
- モノクロ印刷でも読みやすいコントラスト

## カスタマイズのヒント

### 色のカスタマイズ

`resume_print.css` の `:root` セクションで色を変更できます：

```css
:root {
  --primary-color: #2563eb;  /* メインカラー */
  --secondary-color: #1e40af; /* サブカラー */
  --text-color: #1f2937;      /* テキスト色 */
  --tag-bg: #dbeafe;          /* タグの背景色 */
}
```

### レイアウトの調整

フォントサイズや余白は、CSS内の各セクションで調整できます。

## ライセンス

このテンプレートは自由に使用・改変できます。

### HTML変換方法

```bash
# pandocのインストール
brew install pandoc

# HTML変換（履歴書）
pandoc resume.md -o resume.html --embed-resources --standalone -c resume_print.css

# HTML変換（職務経歴書）
pandoc resume_job_history.md -o resume_job_history.html --embed-resources --standalone -c resume_print.css 
```
