<template>
  <q-layout>
    <q-page>
      <div class='container' style="padding:30px;">
        <!-- first row -->
        <app-first-row></app-first-row>
        <br>
        <div class="row">
          <div style="width:66%;margin-right:20px;">
            <!-- 2nd row 70% -->
            <app-main-chart></app-main-chart>
          </div>
          <div style="width:32%;">
            <!-- 2nd row 30% -->
            <app-doughnut></app-doughnut>
            <br>
            <app-doughnut></app-doughnut>
          </div>
        </div>
      </div>
    </q-page>
  </q-layout>
</template>

<script>
import firstRow from '../components/dashboard/firstRow'
import mainChart from '../components/dashboard/mainChart'
import doughnut from '../components/dashboard/doughnut'
export default {
  name: 'PageAbout',
  components: {
    AppFirstRow: firstRow,
    AppMainChart: mainChart,
    AppDoughnut: doughnut
  }
}
</script>
