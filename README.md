# app
簡単なスケジュール管理のためのアプリケーション
フレームワークNuxt.jsを使用してVueを実装

## Build Setup

```bash
# install dependencies
$ npx create-nuxt-app app
npmのようにグローバルインストールする必要なし

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## How to Create app

UI frameworkオプションとしてVuetify.jsをインストール
`$ npm install -D @nuxtjs/vuetify`

'''nuxt.config.jsに追記
{
  buildModules: [
    '@nuxtjs/vuetify'
  ]
}
'''

DateListItem.vue に表示したい内容は開始日時と終了日時をプロパティで受け取る準備
ライブラリLuxonをnpmコマンドでインストール
https://moment.github.io/luxon/#/

'''npm i -S luxon'''

components/EventEditor.vueでよみこみ
'''import { DateTime } from 'luxon'''
'''default値の設定
export default {
  data () {
    return {
      now: DateTime.now(),
    }
  }
}
'''

components/DateListItem.vueで表示させたいフォーマットを記述
`{{ date.toFormat('yyyy/MM/dd') }}`


コンポーネント内で変更があったときにその変数がリアルタイムで更新されるよう設定。
親コンポーネントから子の v-model に変数を渡しておく

v-modelを自作コンポーネントに実装する





## Special Directories
Single Page Application(SPA)を可能にするrouting
ルーティングライブラリ vue-routerは１ページを１コンポーネントに対応して設定し、Nuxt.jsではこれをさらに簡単に、pagesディレクトリにある１ファイルを１ページに対応するよう構成されている。

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/layouts).


### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).

### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/plugins).

### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/store).
