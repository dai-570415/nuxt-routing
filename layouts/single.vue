<template>
  <div>
    <header>
      <span>single layout</span>
    </header>

    <nav>
      <AppNavigation /><!-- ナビゲーター -->
    </nav>

    <main>
      <nuxt /><!-- pages -->
      <li><nuxt-link to="/">Topに戻る</nuxt-link></li>
    </main>

    <footer>
      footer
    </footer>
  </div>
</template>

<script>
  import AppNavigation from '~/components/AppNavigtion.vue';

  export default {
    components: {
      AppNavigation
    }
  }
</script>

<style>

</style>
