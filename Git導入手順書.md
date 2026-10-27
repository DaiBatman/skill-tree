# Git導入手順書

## 1. Gitとは

Gitはソースコードの変更履歴を管理するための「バージョン管理システム」です。

主な用途

- ソースコードの履歴管理
- 複数人での共同開発
- 過去バージョンへの復元
- GitHubとの連携

Java開発や実務では必須級のツールです。

---

# 2. Gitのインストール

## 2.1 Git公式サイトを開く

以下へアクセスします。

https://git-scm.com/

トップページの

```text
Download for Windows
```

をクリックします。

以下を、参考サイトにしました。

https://qiita.com/Ayuchan/items/f88ce258a203d9be44c8

---

## 2.2 インストーラを実行

ダウンロードしたファイルを実行します。

例

```text
Git-2.xx.x-64-bit.exe
```

Windows DefenderやEdgeから

```text
一般的にダウンロードされていません
```

と表示されることがあります。

公式サイトからダウンロードした場合は、

```text
保持する
```

を選択して続行します。

---

## 2.3 インストール設定

基本的にはデフォルト設定のままで問題ありません。

以下はおすすめ設定です。

### Select Components

デフォルトのまま

```text
Next
```

---

### Choosing the default editor

Visual Studio Codeを使用している場合

```text
Use Visual Studio Code as Git's default editor
```

おすすめです。

未導入なら

```text
Vim
```

のままで可

---

### Adjusting the name of the initial branch

以下を選択

```text
Let Git decide
```

---

### Adjusting your PATH environment

以下を選択

```text
Git from the command line and also from 3rd-party software
```

おすすめです。

これにより

```bash
git
```

コマンドが利用できます。

---

### HTTPS transport backend

以下を選択

```text
Use the OpenSSL library
```

---

### Line ending conversions

以下を選択

```text
Checkout Windows-style, commit Unix-style line endings
```

---

### Terminal Emulator

以下を選択

```text
Use MinTTY
```

---

### Default behavior of git pull

以下を選択

```text
Fast-forward or merge
```

---

### Credential Helper

以下を選択

```text
Git Credential Manager
```

---

## 2.4 インストール完了

```text
Install
```

をクリックし完了を待ちます。

終了後

```text
Launch Git Bash
```

にチェックを入れて起動できます。

---

# 3. Git Bashとは

Git BashはWindows上でLinuxコマンドを利用できるターミナルです。

以下のようなコマンドが利用できます。

```bash
ls
pwd
cd
mkdir
rm
```

またGitコマンドも実行できます。

```bash
git status
git add
git commit
```

---

# 4. Gitの動作確認

Git Bashを起動します。

以下を実行。

```bash
git --version
```

実行例

```bash
git version 2.56.0.windows.4
```

表示されれば成功です。

---

# 5. Gitの初期設定

Gitはコミット時に

- 名前
- メールアドレス

を利用します。

最初に設定しておきます。

---

## ユーザー名設定

```bash
git config --global user.name "Daiki"
```

例

```bash
git config --global user.name "大輝"
```

---

## メールアドレス設定

```bash
git config --global user.email "sample@example.com"
```

例

```bash
git config --global user.email "daiki@example.com"
```

---

## 設定確認

```bash
git config --global --list
```

実行例

```text
user.name=Daiki
user.email=sample@example.com
```

---

# 6. Git Bashの便利設定

## 現在の設定確認

```bash
git config --list
```

---

## デフォルトブランチをmainにする

最近のプロジェクトではmainが主流です。

```bash
git config --global init.defaultBranch main
```

確認

```bash
git config --global --get init.defaultBranch
```

実行結果

```text
main
```

---

## 日本語ファイル名文字化け対策

```bash
git config --global core.quotepath false
```

---

## 改行コード設定

Windows環境でおすすめ

```bash
git config --global core.autocrlf true
```

確認

```bash
git config --global --get core.autocrlf
```

---

# 7. Gitリポジトリ作成

作業フォルダへ移動

```bash
cd ~/Desktop
```

フォルダ作成

```bash
mkdir GitPractice
```

移動

```bash
cd GitPractice
```

Git管理開始

```bash
git init
```

成功例

```text
Initialized empty Git repository
```

---

# 8. Gitの基本操作

## 状態確認

```bash
git status
```

---

## ファイル作成

```bash
touch sample.txt
```

---

## ステージング

```bash
git add .
```

---

## コミット

```bash
git commit -m "初回コミット"
```

---

## 履歴確認

```bash
git log
```

---

# 9. 実務でよく使うコマンド

## リポジトリ取得

```bash
git clone
```

---

## 変更確認

```bash
git status
```

---

## ステージング

```bash
git add
```

---

## コミット

```bash
git commit
```

---

## 最新取得

```bash
git pull
```

---

## サーバへ反映

```bash
git push
```

---

# 10. 学習ロードマップ

Git導入後は以下の順番がおすすめです。

1. Gitインストール
2. Git Bashに慣れる
3. git init
4. git add
5. git commit
6. GitHub登録
7. git push
8. EclipseとGit連携
9. ブランチ運用
10. チーム開発

---

# 覚えるべき最重要コマンド

```bash
git status
git add .
git commit -m "message"
git pull
git push
```

まずはこの5つを使えるようになれば十分です。
