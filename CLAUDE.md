# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## リポジトリ概要

Claude Codeのカスタムスキル（SKILL.md）を管理するリポジトリ。各スキルは `skills/<skill-name>/SKILL.md` に配置される。

## 構成

- `skills/` - カスタムスキル定義。各サブディレクトリに `SKILL.md` を配置
  - スキルは YAML frontmatter（name, description, disable-model-invocation）+ Markdown本文で定義
  - descriptionは日本語で記述する

## スキル作成時のルール

- frontmatterに `name`, `description` を必ず含める
- descriptionはスキルの用途と発動条件がわかるように日本語で記述する
- 手順は番号付きリストで明確に記述する
- 機密情報の取り扱いに関する注意事項があれば明記する
