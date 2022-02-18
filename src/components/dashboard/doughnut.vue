<template>
  <div>
  <q-card inline style="width: 100%;background-color:#F6F6F8;">
    <q-card-title class="relative-position" style="background-color:#F6F6F8;">
      <div class="ellipsis">Half DoughnutChart</div>
      <div slot="right" class="row items-center">
        <q-btn flat @click="fillData()" label="Randomize" />
      </div>
    </q-card-title>
    <q-card-separator />
    <q-card-main>
      <doughnut-chart :width="5" :height="2" :chart-data="datacollection" :options="options"></doughnut-chart>
    </q-card-main>
  </q-card>
  </div>
</template>

<script>
import Doughnut from '../charts/Doughnut'

export default {
  components: {
    DoughnutChart: Doughnut
  },
  data () {
    return {
      datacollection: null,
      options: {
        rotation: 1 * Math.PI,
        circumference: 1 * Math.PI
      }
    }
  },
  mounted () {
    this.fillData()
  },
  methods: {
    fillData () {
      this.datacollection = {
        labels: ['A', 'B', 'C'],
        datasets: [
          {
            backgroundColor: ['#FFD751', '#F1A545', '#35414D'],
            data: [this.getRandomInt(), this.getRandomInt(), this.getRandomInt()]
          }
        ]
      }
    },
    getRandomInt () {
      return Math.floor(Math.random() * (50 - 5 + 1)) + 5
    }
  }
}
</script>
