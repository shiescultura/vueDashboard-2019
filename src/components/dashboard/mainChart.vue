<template>
  <q-card inline style="width: 100%;background-color:#F6F6F8;">
    <q-card-title class="relative-position" style="background-color:#F6F6F8;">
      <div class="ellipsis">Line Chart</div>
      <div slot="right" class="row items-center">
        <q-icon name="code" />
      </div>
    </q-card-title>
    <q-card-separator />
    <q-card-main class="medium">
      <line-chart  ref="count" :width="5" :height="2" :chart-data="datacollection" :options="options"></line-chart>
    </q-card-main>
    <br>
    <q-card-separator />
    <q-card-actions>
      <q-btn flat round dense icon="timer" />
      <q-btn flat @click="fillData()" label="Randomize" />
    </q-card-actions>
  </q-card>
</template>

<script>
import Line from '../charts/LineChart'

export default {
  components: {
    LineChart: Line
  },
  data () {
    return {
      datacollection: null,
      options: {
        fill: true
      }
    }
  },
  mounted () {
    console.log(this.$refs.count)
    this.fillData()
  },
  methods: {
    fillData () {
      this.datacollection = {
        labels: ['2008', '2009', '2010', '2011', '2012', '2013', '2014', '2015', '2016', '2017', '2018'],
        datasets: [
          {
            label: 'A',
            borderColor: '#FFD751',
            fill: false,
            data: [this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt()]
          },
          {
            label: 'B',
            borderColor: '#39CCCC',
            fill: false,
            data: [this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt()]
          },
          {
            label: 'C',
            borderColor: '#F16E03',
            fill: false,
            data: [this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt()]
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

<style>
  .medium {
    /* max-width: 600px;
    margin:  150px auto; */
    margin: 24px;
  }
</style>
