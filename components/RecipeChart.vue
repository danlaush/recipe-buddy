<template>
  <section class="recipe-chart">
    Total time to ready: {{ totalDurationFormatted }}

    <ul>
      <li
        v-for="(task, index) in recipe"
        :key="index"
        :style="'background-color: ' + randomColor() + ';\n' +
                'width: ' + percentOfTotal(task.duration) + 'vw;\n' + 
                'transform: translateX(' + percentOfTotal(task.offset) + 'vw);\n'"
        >
        {{task.task}} ({{task.offset}}, {{percentOfTotal(task.offset)}}% width)
      </li>
    </ul>


    <!-- <table>
      <thead>
        <tr>
          <th>Task name</th>
          <th>Duration</th>
          <th>Offset from start</th>
        </tr>
      </thead>
      <tbody>
        <tr 
          v-for="(task, index) in recipe"
          :key="index">
          <td>{{task.task}}</td>
          <td>{{task.duration}}</td>
          <td>{{task.offset}}</td>
        </tr>
      </tbody>
    </table> -->
  </section>
</template>

<script>
  import randomColor from 'randomcolor'
  import moment from 'moment'

  export default {
    name: 'RecipeChart',
    props: {
      recipe: {
        type: Array,
        required: true
      }
    },
    mounted() {
      // console.log('totalDuration in m:ss', this.totalDurationFormatted)
    },
    computed: {
      totalDurationInMs() {
        return (this.recipe[this.recipe.length-1].duration + this.recipe[this.recipe.length-1].offset) * 1000
      },
      totalDurationFormatted() {
        return moment.utc(this.totalDurationInMs).format('m:ss')
      }
    },
    methods: {
      randomColor() {
        return randomColor()
      },
      percentOfTotal(duration) {
        const percent = duration * 1000 / this.totalDurationInMs
        console.log('percentOfTotal', percent)
        return Math.floor(percent * 100)
      }
    }
  }
</script>

<style lang="scss" scoped>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }

  li {
    margin: 0;
    padding: 30px;
    border-radius: 7px;
    white-space: nowrap;
  }
</style>