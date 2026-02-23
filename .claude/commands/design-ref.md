# デザインリファレンス

このプロジェクトのHTMLページは統一されたデザインシステムに基づいています。
新しいページやコンポーネントを作成・修正する際は、以下の仕様を参照してください。

---

## デザイントークン（CSS変数）

```css
/* カラーパレット */
--gray-50: #f9fafb;  --gray-100: #f3f4f6;  --gray-200: #e5e7eb;
--gray-300: #d1d5db;  --gray-400: #9ca3af;  --gray-500: #6b7280;
--gray-600: #4b5563;  --gray-700: #374151;  --gray-800: #1f2937;
--blue-50: #eff6ff;   --blue-100: #dbeafe;  --blue-200: #bfdbfe;
--blue-400: #60a5fa;  --blue-500: #3b82f6;  --blue-600: #2563eb;
--orange-50: #fff7ed; --orange-100: #ffedd5; --orange-200: #fed7aa;
--orange-400: #fb923c; --orange-500: #f97316; --orange-600: #ea580c;
--red-50: #fef2f2;    --red-100: #fee2e2;   --red-400: #f87171;
--green-500: #22c55e; --green-600: #16a34a;

/* 角丸 */
--radius: 16px;       --radius-sm: 10px;    --radius-pill: 9999px;

/* シャドウ */
--shadow: 0 1px 3px rgba(0,0,0,.08), 0 4px 12px rgba(0,0,0,.05);
--shadow-lg: 0 4px 16px rgba(0,0,0,.1), 0 8px 32px rgba(0,0,0,.06);

/* フォント */
--font: 'Segoe UI', 'Hiragino Kaku Gothic ProN', 'Noto Sans JP', sans-serif;
/* 代替: 'Helvetica Neue', Arial, 'Hiragino Kaku Gothic ProN', Meiryo, sans-serif */
```

---

## 共通スタイルルール

- **背景色**: `#f5f5f0` または `var(--gray-50)` (#f9fafb)
- **テキスト色**: `#333` / `var(--gray-800)`
- **行間**: `line-height: 1.6`
- **最大幅**: `max-width: 1100px〜1400px`、`margin: 0 auto`
- **パディング**: コンテナは `padding: 40px 20px 60px`
- **角丸**: カード `14px〜16px`、小要素 `10px`、バッジ `9999px`(pill)

---

## コンポーネント一覧

### 1. カラムヘッダー（column-header）
- グラデーション背景（色はテーマに応じて変更）
  - オレンジ系: `linear-gradient(135deg, #e07850, #d4603c)`
  - グリーン系: `linear-gradient(135deg, #8a9a7a, #7a8b6a)`
  - ブルー系: `linear-gradient(135deg, #5a7abf, #4565a0)`
- 白テキスト、アイコン+タイトル+出典リンク
- 上部角丸 `14px 14px 0 0`

### 2. プランカード（plan-card）
- 白背景、色付きボーダー `2px solid`
- ヘッダー: プラン名（太字カラー）+ 価格バッジ（pill型、薄い背景）
- 箇条書き: 色付き丸ドット（`::before`）
- ホバー: `box-shadow` + `translateY(-2px)`

### 3. ジェネレーションカード（gen-card）
- 白背景、`box-shadow: var(--shadow)`、`border-radius: 16px`
- カードアイコン（40x40、角丸10px、背景色付き）
- ツールバッジ（pill型）+ 年号
- 箇条書き: `●` マーカー
- フッター: 警告（赤系）またはスパークル（オレンジ系）
- ホバー: `translateY(-4px)` + `shadow-lg`
- クリック可能（`cursor: pointer`）

### 4. ステップカード（step-card）
- 横並び: アイコン（36x36丸）+ テキスト
- ステップ番号バッジ（pill型、小さい）
- ホバー: `translateX(4px)`

### 5. フィーチャーカード（feature-card）
- 左ボーダー `3px solid` でアクセントカラー
- アイコン（36x36角丸）+ タイトル + 説明 + 補足ノート

### 6. チェックリスト（check-list）
- `✓` マーク + ラベル + 説明
- 下部に補足ノート（薄い青背景）

### 7. ワークフローボックス（workflow-box）
- 従来 vs 新方式の比較
- ステップをpill型で横並び、`→` で接続

### 8. 統計ボックス（stats-row）
- 3カラムグリッド
- 大きな数値（24px太字）+ ラベル + サブテキスト

### 9. コールアウトバナー（callout-banner / callout-box）
- 白背景、上部にグラデーションライン（3px）
- またはオレンジボーダー+アイコン付きボックス

### 10. 引用ボックス（quote-box）
- `var(--blue-50)` 背景、青ボーダー
- イタリック体、著者名は右寄せ

### 11. ノートボックス（note-box）
- `#fafaf5` 背景、`#e0ddd5` ボーダー
- 小さいフォントサイズ、薄いグレー文字

---

## レスポンシブ対応

- **768px以下（pricing）**: グリッドを1カラムに
- **900px以下（evolution）**: カード縦並び、矢印90度回転、詳細グリッド1カラム
- **600px以下**: カード幅100%、パディング縮小、見出しサイズ縮小

---

## 参照ファイル

既存のHTMLファイルを直接参照する場合:
- `ai-agent-pricing.html` — 3カラム比較レイアウト（料金比較）
- `ai-coding-evolution.html` — SPA風カード+詳細ページ（進化の解説）
