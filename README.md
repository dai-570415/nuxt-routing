# Nuxtのルーティングをシンプルにまとめてみた
現在Vueのフレームワーク、Nuxt.jsを学習中なので、自分へのメモも兼ねてNuxtのルーティングについてシンプルにまとめてみました。

## Nuxtのルーティングアーキテクチャ

- layouts
- components
- pages

この3フォルダを使います。

### layouts

ベーステンプレート
default.vue（初期ファイル）
single.vue(名称任意)

主に共通で表示させたい部品を入れる
（例）ヘッダー、フッター、コンテンツの大枠タグ　など

[HowTo]

```vue:layouts/default.vue
<nuxt />
```
pagesのファイルが呼び出される
※特に設定は不要

```vue:layouts/default.vue
<AppNavigation />

<script>
  import AppNavigation from '~/components/AppNavigtion.vue';

  export default {
    components: {
      AppNavigation
    }
  }
</script>
```
componentsの中に作成した
ナビゲーションが呼び出される
※インポートとコンポーネント設定必須

### components
ルーティングナビゲーション
ナビゲーションリンクを作成することができる

AppNavigtion.vue(名称任意)

[HowTo]

```vue:components/AppNavigtion.vue
<nuxt-link to="/">home</nuxt-link>
<nuxt-link to="/child">child</nuxt-link>
```

### pages
ルーティングファイル
SPAファイルを格納

このページのみ表示したい部品を入れる

index.vue（初期ファイル）
child.vue(名称任意)

```vue:pages/index.vue
<script>
export default {
    // 何も設定しないとdefault.vue
}
</script>
```

```vue:pages/child.vue
<script>
export default {
    // single.vueが適応される
    layout: 'single'
}
</script>
```

## まとめ
Nuxtのルーティングアーキテクチャには以下3フォルダを使う。
- layouts　ベースのテンプレート
- components　ナビゲーションリンクのコンポーネントを作成
- pages　実際にナビゲーションするファイルを格納

ルーティングに関しては正解はありません。
要件によって最適な構造を見つけていくことが重要です。
ベストプラクティスを考え構成してみてください。