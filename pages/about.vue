<template>
  <main class="container">
    <h1 class="title">
      <nuxt-link 
        to="/"
        class="back">
        &laquo;
      </nuxt-link>
      <span class="title__text">
        About
      </span>
    </h1>
    <div class="content">
      <p>I want something to help me visualise what I need to do, and when, when I’m cooking. There are a lot of steps and I want to make sure everything finishes at the right time for best results. The idea is to always know what I should be doing and optimise how to make everything efficiently.</p>

      <p>Like this <a href="https://www.lifehacker.com.au/2010/12/toms-planner-dinner-chart-plans-your-day-for-holiday-cooking/">article about Tom's Planning used for Christmas Dinner</a>, but on a smaller scale and with a better UI: </p>

      <p>It could be expressed as a Gantt chart, with a series of dependencies and the time it takes to do each thing. The end of the final task is to “serve the food”, and work backward from there. What can be done concurrently? What requires multiple steps of preparation? Is this just project management software in a cooking taxonomy?</p>

      <p>I should be able to save a recipe, a series of “tasks” each with a time and an offset from the start. </p>

      <p>Toasted peanut butter and jam sandwich</p>

      <ul>
        <li>Warm up toastie maker (takes 5:00)</li>
        <li>Pull ingredients and tools out, place bread (takes 2:00, offset 2:00)</li>
        <li>Spread peanut butter (takes 0:30, offset 4:00)</li>
        <li>Spread jam (takes 0:30, offset 4:30)</li>
        <li>Toast (takes 2:00, offset 5:00)</li>
        <li>Put away ingredients and tools (takes 1:30, offset 7:30)</li>
        <li>Plate and serve (takes 0:30, offset 9:00)</li>
      </ul>

      <p>The interface should allow me to drag each step along a timeline, or drag the edges of a task to increase or decrease its time. When a two task start or end times are dragged near each other, the task module interface element being dragged should snap to the </p>

      <p>I should be able to “play back” a recipe. It should highlight “what should I be doing right now” and display important information for that step of the cooking process.  </p>

      <p>I should be able to see other people’s recipes, and save recipes I like to a list. I should be able to adjust those recipes for my own kitchen (e.g. if my oven runs hot, I should be able to change the cooking time or temperature on something).</p>

      <p>Tasks should be free text, but stylistic background images can illustrate various verbs “chop”, “boil”, “fry”. Will help user differentiate and remember tasks while cooking.</p>

      <p>Would also be interesting to see if some of this could be automated. Could pull recipes from recipe websites and extract steps, send through a language processor and try to create tasks for a recipe automatically. Can pull cooking times and temps directly out of the recipe, or put a general number in (“Dice 3 tomatoes = 5 minutes”). Perhaps a “suggested timeline” and I can adjust.</p>

      <p>Could be a good tool to experiment with a voice assistant. Can play a recipe one step at a time through google or Alexa or something. https://developers.google.com/actions/ Should say every step at the right offset time, quieting down other sounds (music, Netflix, youtube) like google maps when giving directions.</p>
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


</style>
