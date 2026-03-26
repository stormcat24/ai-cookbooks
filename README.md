# ai-cookbooks

Claude Codeのカスタムスキル（SKILL.md）を管理するリポジトリ。

## スキル一覧

| スキル | 説明 |
|---|---|
| [git-sync-main](skills/git-sync-main/SKILL.md) | mainブランチに切り替えてリモートの最新状態に同期する |
| [git-create-pr](skills/git-create-pr/SKILL.md) | ブランチ作成からPull Request作成まで一気通貫で行う |
| [git-commit](skills/git-commit/SKILL.md) | 変更内容を分析して適切なコミットメッセージを提案・コミットする |
| [git-review-pr](skills/git-review-pr/SKILL.md) | Pull Requestの差分を取得してコードレビューを実施する |
| [git-cleanup-branches](skills/git-cleanup-branches/SKILL.md) | マージ済みのローカルブランチを一括削除して整理する |
| [git-stash](skills/git-stash/SKILL.md) | 変更の一時退避（stash）の操作をガイドする |
| [git-cherry-pick](skills/git-cherry-pick/SKILL.md) | 特定のコミットを別のブランチにcherry-pickする |

## 使い方

各スキルは Claude Code のスラッシュコマンドとして呼び出せます。

```
/git-commit
/git-create-pr
/git-sync-main
```
