# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 技術スタック

- React 19 + Vite 8 (プレーンJavaScript、TypeScriptは未使用)
- Lint: oxlint (`npm run lint`)
- 状態管理: コンポーネントローカルのstate (`useState`)。外部の状態管理ライブラリは使用しない
- データ永続化: `localStorage` (`task-board:tasks` キー)。バックエンド/DBは持たない
- スタイリング: プレーンCSS (`src/App.css`, `src/index.css`)。CSSフレームワークは使用しない
- デプロイ: GitHub Actions (`.github/workflows/deploy.yml`) で `main` へのpush時に自動ビルド・デプロイ

### コマンド

- `npm run dev` — 開発サーバー起動
- `npm run build` — プロダクションビルド
- `npm run lint` — oxlintによるlint
- `npm run preview` — ビルド結果のローカルプレビュー

## コンポーネントの命名規約

- コンポーネント名はPascalCase (例: `App`)、ファイル名もコンポーネント名と一致させ拡張子は`.jsx`とする
- 1ファイル1コンポーネントを基本とする
- イベントハンドラ名は`addTask`/`toggleTask`/`deleteTask`のように動詞+対象のcamelCaseとする

## デプロイ先

https://meguyasu.github.io/task-board/

## Git運用ルール

- コードに変更を加えた場合は、その都度コミットし、GitHubへpushすること。
  変更をローカルに留めず、都度リモートに反映する運用とする。
- コミットメッセージは変更内容が分かるように簡潔に記述する。
