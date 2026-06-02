# shinkai-search-system-skill

深海サーチシステム用の Codex スキルです。

このスキルは、スタッフ間で共有する private GitHub リポジトリ `shinkai-project/shinkai-search-system` を正本資料として扱い、通常は各スタッフPCのローカルクローンを参照して、深海プロジェクトの資料確認を行うための案内役として使います。

このリポジトリには、深海資料本体は含まれていません。スキルをインストールすることと、深海資料リポジトリへアクセスできることは別です。

## 役割

- 「ノア / Noa」を、深海資料を確認するための軽い呼び名として扱う
- 深海資料を探し、要約し、未確認点を分ける
- 資料にない内容を勝手に確定しない
- 通常は `shinkai-project/shinkai-search-system` のローカルクローンを優先して参照する
- ローカルクローンは読み取り専用ミラーとして扱い、通常回答では編集・commit・pushしない
- ローカルクローンや private GitHub リポジトリにアクセスできない場合は、推測せず権限確認や参照場所の共有を促す
- アクセスできない場合でも、無関係なローカルファイルや作業ログを自動で探さない

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
https://github.com/shinkai-project/shinkai-search-system
```

利用者は、このリポジトリへの閲覧権限を持ち、通常はローカルクローンを作成して使います。

標準的なローカルクローン場所:

```text
~/Documents/GitHub/shinkai-search-system
~/GitHub/shinkai-search-system
```

任意の場所にcloneした場合は、環境変数 `SHINKAI_SEARCH_SYSTEM_PATH` にローカルクローンのパスを設定してください。

Windowsの例:

```powershell
setx SHINKAI_SEARCH_SYSTEM_PATH "C:\Users\ユーザー名\Documents\GitHub\shinkai-search-system"
```

ローカルクローンもGitHub正本も参照できない場合、スキルはローカルファイル、作業ディレクトリ、作業ログ、過去の相談メモを自動で探しません。

ローカル資料を使う場合は、ユーザーが「このファイルを参照して」「このローカル資料を使って」のように、参照対象を明示する必要があります。

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
- 通常回答では、ローカルクローンや正本資料を編集しない
- 通常回答では、`git add`、`git commit`、`git push` を行わない
- ローカルクローンやGitHub正本にアクセスできないことを理由に、無関係なローカル資料へ自動で切り替えない
- 公開状況が資料内に書かれていない場合は「未整理」と扱う
