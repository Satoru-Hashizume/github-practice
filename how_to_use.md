\# Git / GitHub メモ



\## GitHubとは



GitHubは、プログラムやデータ、文章などを置いておくオンラインの保管庫。



1つのプロジェクト単位を \*\*リポジトリ\*\* と呼ぶ。



例：



```text

Satoru-Hashizume / github-practice

```



これは、`Satoru-Hashizume` というアカウントが、`github-practice` というリポジトリを持っているという意味。



\---



\## Gitとは



Gitは、ファイルの変更履歴を管理する仕組み。



GitHubは、そのGitで管理したファイルをネット上に置くサービス。



```text

Git = 変更履歴を管理する仕組み

GitHub = Gitで管理したファイルをネット上に置く場所

```



\---



\## Git Bashとは



Git Bashは、WindowsでGitを操作するためのコマンド入力画面。



コマンドプロンプトに近いもの。



よく使う基本コマンド：



```bash

pwd

```



今いる場所を確認する。



```bash

ls

```



今いるフォルダの中身を見る。



```bash

cd フォルダ名

```



指定したフォルダに移動する。



\---



\## WindowsとGit Bashのフォルダ表記



Windowsでは：



```text

C:\\Users\\Satoru\\github-practice

```



Git Bashでは：



```bash

/c/Users/Satoru/github-practice

```



同じ場所を違う書き方で表している。



\---



\## cloneとは



GitHub上のリポジトリを、自分のPCにコピーする操作。



```bash

git clone リポジトリURL

```



例：



```bash

git clone https://github.com/Satoru-Hashizume/github-practice.git

```



この場合、今いるディレクトリの中に `github-practice` フォルダが作られる。



保存先を指定したい場合：



```bash

git clone リポジトリURL 保存先フォルダ

```



例：



```bash

git clone https://github.com/Satoru-Hashizume/github-practice.git /c/Users/Satoru/Documents/SpyderProjects/github-practice

```



\---



\## PCで編集した内容をGitHubに反映する流れ



まず状態確認：



```bash

git status

```



変更したファイルをcommit対象にする：



```bash

git add .

```



または、特定ファイルだけなら：



```bash

git add hello.py

```



変更履歴として保存する：



```bash

git commit -m "Update hello.py"

```



GitHubへ送る：



```bash

git push

```



\---



\## GitHub側の変更をPCに取り込む



GitHub上で編集した内容をPCに取り込むときは：



```bash

git pull

```



\---



\## 基本サイクル



```text

PCで編集する

↓

git status で確認

↓

git add .

↓

git commit -m "変更内容のメモ"

↓

git push

↓

GitHubに反映

```



\---



\## よく出たエラー



\### add: command not found



間違い：



```bash

add hello.py

```



正しい：



```bash

git add hello.py

```



`add` だけではなく、前に `git` が必要。



\---



\### Author identity unknown



Gitに名前とメールが設定されていない状態。



初回だけ以下を設定する。



```bash

git config --global user.name "Satoru"

git config --global user.email "petrinet0912@gmail.com"

```



その後、もう一度commitする。



\---



\## Spyderとの関係



GitHubはPythonを実行する場所ではない。



```text

GitHub = コードを保存・共有・履歴管理する場所

Spyder / Jupyter = Pythonコードを編集・実行する場所

```



おすすめの流れ：



```text

GitHubからclone

↓

Spyderで開いて編集・実行

↓

Git Bashで add / commit / push

↓

GitHubに保存

```



