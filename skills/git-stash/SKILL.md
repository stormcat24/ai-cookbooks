---
name: git-stash
description: 変更の一時退避（stash）操作を行う。「一時退避して」「stashして」「変更を退避」「stash見せて」「退避した変更を戻して」「stash一覧」「stash popして」「stash dropして」など、git stashに関するあらゆる操作で使用する。引数なしで退避、list/pop/drop/showなどの操作を引数で指定できる。
disable-model-invocation: true
---

変更の一時退避（git stash）を安全に操作するスキル。退避・一覧表示・復元・削除をガイドする。

## 手順

1. `$ARGUMENTS` と文脈から実行したい操作を判断する
   - 引数なし or 「退避して」→ **save**
   - 「一覧」「見せて」「list」→ **list**
   - 「戻して」「復元して」「pop」→ **pop**
   - 「適用して」「apply」→ **apply**
   - 「消して」「drop」→ **drop**
   - 「中身見せて」「show」→ **show**

### save（退避）
2. `git status` で変更内容を確認する
   - 変更がない場合はその旨を伝えて終了する
3. `git stash push -m "<説明>"` で変更を退避する
   - 説明は変更内容を簡潔に表現したものを自動生成する
   - `$ARGUMENTS` にメッセージが指定されていればそれを使用する
   - 未追跡ファイルも含めたい場合は `-u` オプションを付ける（ユーザーに確認）
4. 退避完了を報告する

### list（一覧）
2. `git stash list` で退避中の変更一覧を表示する
3. 各エントリの概要をわかりやすく表示する

### pop（復元して削除）
2. `git stash list` で一覧を表示する
3. 複数ある場合はどれを復元するかユーザーに確認する
4. `git stash pop [stash@{n}]` で復元する
   - コンフリクトが発生した場合はその旨を伝え、解決方法を案内する

### apply（復元して保持）
2. `git stash list` で一覧を表示する
3. 複数ある場合はどれを適用するかユーザーに確認する
4. `git stash apply [stash@{n}]` で適用する（stashは残る）

### drop（削除）
2. `git stash list` で一覧を表示する
3. どれを削除するかユーザーに確認する（`git stash drop` は取り消せないため必ず確認）
4. `git stash drop [stash@{n}]` で削除する

### show（内容確認）
2. `git stash list` で一覧を表示する
3. `git stash show -p [stash@{n}]` で差分を表示する
