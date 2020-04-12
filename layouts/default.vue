<template>
  <div>
    <header>
      <span>defult layout</span>
    </header>

    <nav>
      <AppNavigation /><!-- ナビゲーター -->
    </nav>

    <main>
      <nuxt /><!-- pages -->
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
