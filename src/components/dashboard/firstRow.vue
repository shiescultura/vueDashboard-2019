<template>
  <div class="row" >
    <div style="width:34%; padding-right:20px;">
  <!-- card -->
      <q-card inline style="width:100%;background-color:#FFD751;">
        <q-card-title>
          USERS
          <span slot="subtitle">From last week</span>
          <q-icon slot="right" name="people"  color="dark"/>
        </q-card-title>
        <q-card-main>
          <h1 style="weight:300;color:54;float:right;margin-top:-40px;color:#ffffff;" class="q-display-3">
            <countTo :startVal='startVal' :endVal='89000' :duration='5000'></countTo>
          </h1>
        </q-card-main>
      </q-card>
    </div>
    <div style="width:34%; padding-right:20px;">
  <!-- card -->
      <q-card inline style="width:100%;background-color:#F16E03;">
        <q-card-title>
          COMMENTS
          <span slot="subtitle">Number of jobs</span>
          <q-icon slot="right" name="comment" />
        </q-card-title>
        <q-card-main>
          <h1 style="weight:300;color:54;float:right;margin-top:-40px;color:#ffffff;" class="q-display-3">
            <countTo :startVal='startVal' :endVal='15823' :duration='5000'></countTo>
          </h1>
        </q-card-main>
      </q-card>
    </div>
    <div style="width:32%; padding-right:5px;">
  <!-- card -->
      <q-card inline style="width:100%;background-color:#39CCCC;">
        <q-card-title>
          LIKES
          <span slot="subtitle">Number of jobs</span>
          <q-icon slot="right" name="thumb_up" />
        </q-card-title>
        <q-card-main>
          <h1 style="weight:300;color:54;float:right;margin-top:-40px;color:#ffffff;" class="q-display-3">
            <countTo :startVal='startVal' :endVal='6933' :duration='5000'></countTo>
          </h1>
        </q-card-main>
      </q-card>
    </div>
  </div>
</template>

<script>
import countTo from 'vue-count-to'

export default {
  components: { countTo },
  data () {
    return {
      startVal: 0,
      endVal: 0
    }
  }
}
</script>
