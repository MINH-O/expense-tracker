# ミニマル支出分類 (Minimal Expense Tracker)

AI (Gemini API) を活用し、日常の自然な文章から「項目」「金額」「カテゴリ」を自動抽出・分類する家計簿Webアプリケーションです。

## 🚀 主要機能 (Features)
- **AI 自動抽出:** 「お昼に豚骨ラーメン1200円食べた」のような自然なテキストを入力するだけで、LLMがデータを構造化して抽出します。
- **多言語対応 (i18n):** 日本語(JP)と英語(EN)のUI切り替えが可能です。言語に合わせてAIへのシステムプロンプトも動的に変化します。
- **リアルタイム集計:** 入力されたデータは即座にテーブルに追加され、総支出額とカテゴリ別の合計が自動計算されます。

## 🛠 技術スタック (Tech Stack)
- **Frontend:** HTML5, Vanilla JavaScript, Tailwind CSS
- **AI / API:** Google Gemini API (gemini-2.5-flash-preview)

## 💡 技術的な工夫・アピールポイント (Technical Highlights)
1. **APIの安定性向上 (Exponential Backoff):** 一時的なネットワークエラーやAPIのレート制限に備え、指数バックオフ(Exponential Backoff)を用いたリトライロジックを実装し、フロントエンド側の堅牢性を高めました。
2. **LLMのレスポンス制御 (JSON Schema):** LLM特有のテキストパースエラーを未然に防ぐため、APIリクエスト時にレスポンスのMIMEタイプを `application/json` に指定し、厳密なJSON配列フォーマットのみを返すように制御しています。
3. **Vanilla JSによる軽量な状態管理:** Reactなどの外部フレームワークに依存せず、純粋なJavaScriptのみでデータ状態(State)の管理と多言語UIのDOMレンダリングを同期させるアーキテクチャを構築しました。
