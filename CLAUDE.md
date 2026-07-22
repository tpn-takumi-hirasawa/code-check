# CLAUDE.md

Claude Code がこのプロジェクトで従う共通ルール、プロジェクト概要、開発手順を定義します。

## プロジェクト概要

**プロジェクト名**: code-check

**目的**: Claude Code を活用して、ソフトウェア開発における仕様作成、設計、実装、コードレビュー、テスト、ドキュメント更新を支援するためのリポジトリ

**技術スタック**: TBD

**対象システム**: TBD

## ドキュメント保存場所

| ドキュメント | 保存場所 | 責務 |
|---------|--------|------|
| プロジェクト概要 | `docs/project-brief.md` | プロジェクトの目的、利用者、スコープ |
| 開発ワークフロー | `docs/development-workflow.md` | 開発手順、フロー、チェックリスト |
| 用語辞書 | `docs/glossary.md` | 用語定義、ドメイン概念 |
| 機能仕様書 | `docs/specs/` | 機能の振る舞いと受入条件 |
| 技術設計書 | `docs/design/` | 技術的な実現方法 |
| 技術判断記録 | `docs/adr/` | 重要な技術判断と理由 |
| カスタムエージェント | `.claude/agents/` | 専門エージェントの定義 |
| 領域別ルール | `.claude/rules/` | 領域別開発ルール |
| 再利用スキル | `.claude/skills/` | 再利用可能な作業フロー |

## 開発手順

Claude Code での開発は、以下の工程に従います：

1. **要求整理**: `requirements-analyst` を使用
2. **仕様書作成**: `spec-writer` を使用
3. **仕様レビュー**: 仕様書を確認し承認
4. **設計書作成**: `design-writer` を使用
5. **設計レビュー**: 設計書を確認し承認
6. **実装計画**: `implementation-planner` を使用
7. **実装**: 実装対象のコードを作成
8. **コードレビュー**: `code-reviewer` を使用
9. **テスト**: `test-writer` を使用
10. **ドキュメント更新**: `docs-maintainer` を使用
11. **Pull Request 作成**: `pr-writer` を使用

## コーディング規約

TBD

## テスト方針

- **単体テスト**: TBD
- **統合テスト**: TBD
- **テストカバレッジ**: TBD
- **テスト実行コマンド**: TBD

## ドキュメント更新方針

- 仕様、設計に影響する変更では、実装と同時に関連ドキュメントを確認する
- コードとドキュメントを同期させる
- 個別機能の詳細仕様は、`CLAUDE.md` ではなく対応する仕様書に記載する

## 基本方針

### 推測で仕様を確定しない

不明な業務ルールや要件は、Claude Code に推測させず、`TBD` または未決事項として記録します。

### 仕様と設計を分離する

- 仕様書には利用者から見た振る舞いを記載
- 具体的な実装方法は設計書に記載

### 実装前に計画する

複数ファイルに影響する変更では、実装前に影響範囲、変更対象、テスト方針を整理します。

### レビュー担当はコードを変更しない

- コードレビューとコード修正を分離
- レビュー結果を確認してから修正

### テストを成功させるために実装を歪めない

テスト担当は、テストを通すために本体コードを変更したり、アサーションを弱めたりしません。

### 実行していない検証を成功と報告しない

テスト、lint、ビルドなどについて、実際に実行した結果のみを記録します。

## 禁止事項

- 不明な要件を推測で実装する
- 仕様なしで設計書を作成する
- 設計なしでコードを実装する
- 受入テストなしで実装を完了とする
- テストを通すために本体コードを変更する

## 検証コマンド

TBD

## カスタムエージェント

このプロジェクトでは、以下のカスタムエージェントを定義しています：

| エージェント | 役割 | ファイル |
|-----------|------|--------|
| `requirements-analyst` | 要求の整理、前提・制約・未決事項の抽出 | `.claude/agents/requirements-analyst.md` |
| `spec-writer` | 機能仕様書の作成・更新 | `.claude/agents/spec-writer.md` |
| `design-writer` | 技術設計書の作成・更新 | `.claude/agents/design-writer.md` |
| `implementation-planner` | 実装対象と実装順序の整理 | `.claude/agents/implementation-planner.md` |
| `code-reviewer` | コード差分のレビュー | `.claude/agents/code-reviewer.md` |
| `code-improver` | 可読性、保守性、安全性の改善 | `.claude/agents/code-improver.md` |
| `test-writer` | テストの作成、追加、評価 | `.claude/agents/test-writer.md` |
| `security-reviewer` | 認証、認可、入力検証などの確認 | `.claude/agents/security-reviewer.md` |
| `docs-maintainer` | コードとドキュメントの整合性確認 | `.claude/agents/docs-maintainer.md` |
| `pr-writer` | Pull Request の説明文作成 | `.claude/agents/pr-writer.md` |

## 領域別ルール

TBD

## 再利用スキル

TBD

## 今後の作業

- [ ] CLAUDE.md の詳細作成
- [ ] `docs/project-brief.md` の作成
- [ ] `docs/development-workflow.md` の作成
- [ ] `docs/glossary.md` の作成
- [ ] カスタムエージェントの定義
- [ ] 領域別ルールの定義
- [ ] 再利用スキルの定義
