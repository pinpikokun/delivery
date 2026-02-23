# HTMLページ生成

ユーザーの指示に基づいて、このプロジェクトのデザインシステムに沿ったHTMLページを生成してください。

## 必須手順

1. まず既存のHTMLファイルを参照してデザインパターンを確認する:
   - `ai-agent-pricing.html` — 比較・料金系レイアウトの参考
   - `ai-coding-evolution.html` — 解説・ストーリー系レイアウトの参考

2. 以下のデザインルールを厳守する

## デザインルール

### 基本構造
- `<!DOCTYPE html>` + `<html lang="ja">`
- meta charset UTF-8 + viewport設定
- CSSはすべて `<style>` タグ内にインライン（外部CSSなし）
- JavaScriptも `<script>` タグ内にインライン（外部JSなし）
- 単一HTMLファイルで完結させる

### カラーパレット
- 背景: `#f5f5f0` または `#f9fafb`
- テキスト: `#333` / `#1f2937`
- アクセント:
  - オレンジ系: `#f97316`, `#ea580c`, `#e07850`
  - ブルー系: `#3b82f6`, `#2563eb`, `#5a7abf`
  - グリーン系: `#22c55e`, `#8a9a7a`
  - パープル系: `#6a5aaa`
  - グレー系: `#6b7280`, `#9ca3af`, `#d1d5db`

### タイポグラフィ
- フォント: `'Segoe UI', 'Hiragino Kaku Gothic ProN', 'Noto Sans JP', sans-serif`
- 見出し: 太字 700-800、サイズ 1.15rem〜42px
- 本文: 0.85rem〜0.95rem、`line-height: 1.6〜1.7`
- バッジ: 12px〜13px、`font-weight: 600`

### コンポーネントスタイル
- **カード**: 白背景、角丸 14px〜16px、`box-shadow: 0 1px 3px rgba(0,0,0,.08), 0 4px 12px rgba(0,0,0,.05)`
- **バッジ/タグ**: `border-radius: 9999px`（pill型）、薄い背景色+濃いテキスト色
- **ボーダーカラーカード**: `border: 2px solid` + テーマカラーの薄い色
- **ヘッダーバー**: `linear-gradient(135deg, ...)` のグラデーション背景、白テキスト
- **アイコン**: 36px〜40px、角丸6px〜50%、薄い背景色
- **ホバー**: `translateY(-2px〜-4px)` + シャドウ強化、`transition: 0.15s〜0.2s`

### レイアウト
- **コンテナ**: `max-width: 1100px〜1400px`、`margin: 0 auto`、`padding: 40px 20px 60px`
- **グリッド**: `display: grid`、`gap: 28px〜32px`
- **カード並び**: `display: flex` + `gap: 12px〜16px`
- **レスポンシブ**: 768px〜900px以下で1カラム化

### レスポンシブ対応（必須）
```css
@media (max-width: 900px) {
  /* グリッドを1カラムに */
  /* フォントサイズ縮小 */
  /* パディング縮小 */
}
@media (max-width: 600px) {
  /* カード幅100% */
  /* さらに余白縮小 */
}
```

### SVGアイコン
- インラインSVGを使用（外部アイコンライブラリ不要）
- `width="16〜20" height="16〜20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"`

## コンテンツタイプ別テンプレート選択

ユーザーのリクエストに応じて適切なレイアウトを選択:

- **比較系**（料金、スペック比較）→ `ai-agent-pricing.html` パターン
  - 3カラムグリッド、カラムヘッダー、プランカード
- **解説系**（進化、ストーリー、機能紹介）→ `ai-coding-evolution.html` パターン
  - カード横並び→詳細ページ、ステップカード、フィーチャーカード
- **混合** → 両方のコンポーネントを組み合わせ

## 出力

- ファイル名: ユーザー指定、またはテーマに基づいた英語ケバブケースの `.html`
- 出力先: プロジェクトルート（`C:\Users\admin\Desktop\work\delivery\`）
- 日本語コンテンツ前提（`lang="ja"`）

$ARGUMENTS
