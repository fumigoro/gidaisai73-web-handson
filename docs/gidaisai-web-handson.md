---
title: 岐大祭広報局Web担当 勉強会
auther: fumigoro
---

## 岐大祭広報局Web担当 勉強会 環境構築編

# VSCodeのインストール

公式サイトからインストールするだけ。

[https://azure.microsoft.com/ja-jp/products/visual-studio-code/](https://azure.microsoft.com/ja-jp/products/visual-studio-code/)


# WSLの有効化
Windows上で、開発に便利なLinuxの環境を立てられるという機能。
2年ほど前に登場し、かなりいい感じに使えるようになってきているので採用する。


最近公式サイトに載っているコマンド1つで有効化出来るようになった。（スバラシイ！）
[https://docs.microsoft.com/ja-jp/windows/wsl/install](https://docs.microsoft.com/ja-jp/windows/wsl/install)

# Windows Terminalのインストール
WSLの標準のターミナルはフォントが見づらい上に1個しか開けないため、高機能なWindows Terminal を使う。

こちらもMicrosoft StoreからインストールするだけでOK！（カンタン！）

[https://www.microsoft.com/ja-jp/p/windows-terminal/9n0dx20hk701](https://www.microsoft.com/ja-jp/p/windows-terminal/9n0dx20hk701)

インストールしたら、タブ部分の下向き「く」マークみたいなのをクリックし「settings」を開く。

「Default profile」をよく使う「Ubuntu」に設定しておこう。
これでWindows Terminal を立ち上げたときにUbuntuのターミナルが起動するようになる。

# Node.jsのインストール
Web関係の開発をするなら絶対に必要になるNode.jsの環境を用意する。

先に以下のコマンドでインストール済みのパッケージを更新しておこう。
（最初は何かをインストールする前にやるお作法という理解でOK!）
`Do you want to continue? `と聞かれたら`Y`と入力しEnter！

```bash
sudo apt update
sudo apt upgrade
```

続いてNode.jsのバージョン管理をしてくれる`nvm`を先にインストールする。
Node.jsはバージョンアップの頻度が高いので、複数のバージョンを共存させて切り替えられる`nvm`を利用するのがオススメ。

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```
以下のコマンドでバージョンが表示されればインストール成功
```bash
nvm --version
```

続いてNode.jsのインストール。今の最新版`14.18.0`がインストールされる。
現在の最新版は公式サイトで確認可能。

[https://nodejs.org/ja/](https://nodejs.org/ja/)

```
nvm install --lts
```
Node.jsをインストールすると、パッケージマネージャーのnpmが同梱されてくる・
以下のコマンドでNode.jsとnpmがインストールされたことを確認しよう。
```
node --version
npm --version
```

# VScode拡張機能のインストール

## Remote - WSL
WSLを使う上では必須の拡張機能

[https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)

# GitHubアカウントの作成
[https://github.com/](https://github.com/)

# Git のインストールと設定

参考：[https://docs.microsoft.com/ja-jp/windows/wsl/tutorials/wsl-git](https://docs.microsoft.com/ja-jp/windows/wsl/tutorials/wsl-git)
```Bash
sudo apt install git
```
インストールできたら、以下のコマンドでユーザー名とメールアドレスを設定しよう。ユーザー名はGitHubのIDに設定する（別に違ってても問題ない）
```
# ユーザー名の設定
git config --global user.name "Your Name"
```

メールアドレスに関しては、普段遣いのものを登録すると意図せず公開されてしまい迷惑メールが送りつけられてしまう可能性もあるため、Githubで発行できるコミット用のメールアドレスを設定すると良い
[https://docs.github.com/ja/account-and-profile/setting-up-and-managing-your-github-user-account/managing-email-preferences/setting-your-commit-email-address](https://docs.github.com/ja/account-and-profile/setting-up-and-managing-your-github-user-account/managing-email-preferences/setting-your-commit-email-address)

```
# メールアドレスの設定
git config --global user.email "youremail@domain.com"
```

以上で基本的な環境構築は完了です。
かなりガッツリとプログラミングができる環境が整いました。

お疲れさまでした！




