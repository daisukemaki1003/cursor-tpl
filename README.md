# Cursor Rules プロンプト集

このワークスペースでは、開発効率を向上させるためのプロンプトルールを管理しています。

## 📁 ディレクトリ構成

```
.
├── .cursor/
│   └── rules/            # プロンプトファイル群
│       ├── static/       # 静的サイト開発用
│       │   ├── entry-point.mdc     # エントリーポイント
│       │   ├── frontend.mdc        # HTML/SCSS開発用
│       │   ├── typescript.mdc      # TypeScript開発用
│       │   └── design-to-code.mdc  # デザイン画像からコード生成用
│       └── next/         # Next.js開発用
│           ├── entry-point.mdc     # エントリーポイント
│           ├── regulation.mdc      # Next.js開発用
│           └── design-to-code.mdc  # デザイン画像からコード生成用
└── README.md             # このファイル
```

## 🎯 プロンプトの種類

### 静的サイト開発用（`static/`）

#### エントリーポイント（`static/entry-point.mdc`）

- **用途**: 静的サイト開発の基本ルール
- **特徴**: 他のプロンプトファイルを参照する仕組み

#### HTML/SCSS 開発用（`static/frontend.mdc`）

- **用途**: デザイン画像なしの HTML/SCSS 開発
- **特徴**:
  - セマンティックな HTML5 構造
  - SCSS 記法でのスタイリング
  - レスポンシブ対応
  - BEM 記法ベースの命名規則
  - 再利用可能なコンポーネント設計
  - **デザイン画像がある場合は自動的に `design-to-code.mdc` を参照**

#### TypeScript 開発用（`static/typescript.mdc`）

- **用途**: TypeScript プロジェクトの開発
- **特徴**:
  - 型安全性を重視したコード設計
  - インターフェースとタイプエイリアスの適切な使用
  - クラス設計とエラーハンドリング
  - モジュール設計とテスト対応

#### デザイン画像からコード生成用（`static/design-to-code.mdc`）

- **用途**: デザイン画像を分析して HTML/SCSS を生成
- **特徴**:
  - `frontend.mdc` を参照して基本ルールを適用
  - 画像からの色・フォント・スペーシングの正確な抽出
  - レイアウト分析と忠実な再現
  - デザイン分析結果の明示的な出力
  - カラーコードや数値の正確な指定

### Next.js 開発用（`next/`）

#### エントリーポイント（`next/entry-point.mdc`）

- **用途**: Next.js 開発の基本ルール
- **特徴**: 他のプロンプトファイルを参照する仕組み

#### Next.js 開発用（`next/regulation.mdc`）

- **用途**: Next.js 14 以降、TypeScript、Tailwind CSS、shadcn/ui を使用した開発
- **特徴**:
  - App Router を使用した構成
  - TypeScript による型安全性
  - Tailwind CSS でのスタイリング
  - shadcn/ui コンポーネントの活用
  - 適切なディレクトリ構成
  - **デザイン画像がある場合は自動的に `design-to-code.mdc` を参照**

#### デザイン画像からコード生成用（`next/design-to-code.mdc`）

- **用途**: デザイン画像を分析して Next.js コードを生成
- **特徴**:
  - `regulation.mdc` を参照して基本ルールを適用
  - Next.js、TypeScript、Tailwind CSS、shadcn/ui を使用
  - デザインの忠実な再現
  - 適切なコンポーネント分割
  - ファイル構成の設計

## 🚀 使用方法

### 基本的な使用方法

1. 開発したい内容に応じて、適切なエントリーポイントファイルを参照
   - 静的サイト: `static/entry-point.mdc`
   - Next.js: `next/entry-point.mdc`
2. エントリーポイントが自動的に必要なプロンプトファイルを参照
3. 各プロンプトのルールに従ってコードを生成

### プロンプトの選択基準

#### 静的サイト開発

- **HTML/SCSS 開発**: `static/frontend.mdc`
- **TypeScript 実装**: `static/typescript.mdc`
- **デザイン画像あり**: `static/frontend.mdc`（自動的に `design-to-code.mdc` を参照）

#### Next.js 開発

- **一般的な Next.js 開発**: `next/regulation.mdc`
- **デザイン画像あり**: `next/regulation.mdc`（自動的に `design-to-code.mdc` を参照）

### 参照例

#### 静的サイトでアコーディンのアニメーションを TypeScript で実装

1. `static/entry-point.mdc` を読み込み
2. その後 `static/typescript.mdc` を読み込み

#### Next.js でデザイン画像からコンポーネント生成

1. `next/entry-point.mdc` を読み込み
2. その後 `next/regulation.mdc` を読み込み（自動的に `design-to-code.mdc` も参照）

## 📋 共通ルール

すべてのプロンプトで共通するルール：

- 日本語でのコミュニケーション
- セマンティックな HTML 構造
- アクセシビリティを考慮した実装
- レスポンシブデザイン対応
- 再利用可能なコンポーネント設計
- 最新の Google Chrome 基準でのブラウザサポート

## 🔧 カスタマイズ

各プロンプトファイルは独立して編集可能です。必要に応じて：

1. 新しいプロンプトファイルを追加
2. 既存のプロンプトを修正
3. エントリーポイントファイルで参照を更新

## 📝 注意事項

- プロンプトファイルは Markdown 形式で記述
- コード例は実際の開発で使用可能な形式で記載
- 各プロンプトの前提条件を必ず確認してから使用
- 必要に応じてプロジェクト固有の設定を追加

## 🤝 貢献

プロンプトの改善や新しいプロンプトの追加は歓迎します。以下の点を考慮してください：

- 明確で実用的なルール
- 具体的なコード例
- 日本語での説明
- 最新のベストプラクティスに準拠
