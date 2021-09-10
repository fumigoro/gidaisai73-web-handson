# 岐大祭会場ウェブサイトの試作・ハンズオン

## セットアップ

```bash

## このリポジトリをclone
$ git clone https://github.com/fumigoro/gidaisai73-web-handson.git

# cloneしたリポジトリへ移動
$ cd gidaisai73-web-handson

# install dependencies
# 依存関係を一括インストール
$ npm install

# serve with hot reload at localhost:3000
# ホットリロードサーバーをlocalhost:3000に立てる
$ npm run dev

# generate static project
# 静的ファイルを生成する(今回はこっちを使用)
$ npm run generate
```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## 技術スタック

### `Nuxt.js`

Vue.jsフレームワーク。`/pages`配下の.vueファイルに基づき、HTMLを生成する。Type

### `nuxt/content`

NuxtのCMSモジュール。

`/content/groups`配下の各団体のjsonファイルのデータを`pages/groups/_slug.vue`に1つずつ当てはめ、`pages/groups/{団体のid}`というパスでHTMLを生成する。

### `nuxtjs/google-fonts`

google fontsの読み込みに使用。`/nuxt.config.js`の`buildModules`で読み込むフォントファミリーを指定している。

### `bootstrap`

CSSフレームワーク

## ディレクトリの役割

### `assets`

共通のCSSファイルを入れてます

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`


プロジェクト内で繰り返し用いるVue.jsのコンポーネントファイルを入れます。ヘッダーやフッダー、ナビゲーションなど。

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `pages`

ここの中身の構造が、生成されるWebサイトのディレクトリ構造になります。各ページを構成する.vueファイルを入れます。ファイルの先頭に`_`がつくファイルは、Nuxt/contentのテンプレートのような役割をします。

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).


### `static`

画像などの静的ファイルを入れます。このディレクトリは`/`のようにルートディレクトリとしてマッピングされるので、この内のファイルは、.vueの中では`/image/hoge.png`のようにアクセスできます。
This directory contains your static files. Each file inside this directory is mapped to `/`.

例：`/static/robots.txt`は`/robots.txt`としてアクセスできます。

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

