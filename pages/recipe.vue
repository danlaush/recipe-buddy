<template>
  <section>
    <div class="container">
      <h1 class="title">
        <nuxt-link 
          to="/">
          &laquo;
        </nuxt-link>
        <span>
          🥪 Toasted PB&amp;J
        </span>
      </h1>
      <p>
        See the recipe below
      </p>
    </div>
    <recipe-chart 
      :recipe="recipe" />
  </section>
</template>

<script>
  import RecipeChart from '~/components/RecipeChart.vue'

  const recipe = [
    {
      task: "Warm up toastie maker",
      duration: 300,
      offset: 0
    },
    {
      task: "Pull ingredients and tools out, place bread",
      duration: 120, 
      offset: 120
    },
    {
      task: "Spread peanut butter",
      duration: 30, 
      offset: 240
    },
    {
      task: "Spread jam",
      duration: 30, 
      offset: 270
    },
    {
      task: "Toast",
      duration: 120, 
      offset: 300
    },
    {
      task: "Put away ingredients and tools",
      duration: 90, 
      offset: 450
    },
    {
      task: "Plate and serve",
      duration: 30, 
      offset: 540
    },
  ]

  export default {
    async asyncData ({ params }) {
      return {
        recipe
      }
    },
    components: {
      RecipeChart
    }
  }
</script>

<style lang="scss" scoped>
  @import "../static/styles/index.scss";
</style>
