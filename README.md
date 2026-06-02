# shinkai-search-system-skill

深海サーチシステム用の Codex スキルです。

このスキルは、スタッフ間で共有する private GitHub リポジトリ `AkiSaikawa/shinkai-search-system` を正本資料として参照し、深海プロジェクトのキャラクター、区域、組織、用語、物語、公開状況、仮設定、世界観判断を確認するための案内役として使います。

## 役割

- 「ノア / Noa」を、深海資料を確認するための軽い呼び名として扱う
- 深海資料を探し、要約し、未確認点を分ける
- 資料にない内容を勝手に確定しない
- private GitHub リポジトリにアクセスできない場合は、推測せず権限確認を促す

## インストール

Codex の skill installer を使う場合:

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo AkiSaikawa/shinkai-search-system-skill --path shinkai-search-system-skill
```

手動で入れる場合:

1. このリポジトリをダウンロードまたは clone する
2. `shinkai-search-system-skill` フォルダを Codex の skills フォルダへコピーする
3. Codex を再起動する

Windows の標準的な配置例:

```text
C:\Users\<user>\.codex\skills\shinkai-search-system-skill
```

## 前提

このスキル自体には、深海の世界設定本文は入っていません。

正本資料は以下の private GitHub リポジトリです。

```text
https://github.com/AkiSaikawa/shinkai-search-system
```

利用者は、このリポジトリへの閲覧権限、GitHub 連携、または資料ファイルへのアクセス手段を持っている必要があります。

## 呼び出し例

```text
ノア、アオについて教えて
ノア、D区の設定を確認して
ノア、教団ゼロについてまとめて
ノア、この設定は深海らしい？
ノア、この情報は公開済み？
```

## 注意

- 正史判断、公開判断、採用判断はユーザーが行う
- チャット履歴や作業ログを正本資料として扱わない
- 公開状況が資料内に書かれていない場合は「未整理」と扱う
