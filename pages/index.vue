<template>
  <main class="container">
    <app-logo/>
    <h1 class="title">
      Recipe Buddy
    </h1>
    <h2 class="subtitle">
      Visualise and verbalize your recipes
    </h2>
    <div class="links">
      <nuxt-link
        to="/recipe"
        class="button--green">View a recipe</nuxt-link>
      <nuxt-link
        to="/about"
        class="button--grey">About</nuxt-link>
    </div>
  </main>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  }
}
</script>

<style lang="scss" scoped>
  @import "../static/styles/index.scss";

  .container {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
</style>
