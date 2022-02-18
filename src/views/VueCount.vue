<template>
  <q-page>
    <div class='container' style="padding:30px;">
      <div class="row">
        <h5>Vue CountTo</h5>
      </div>
      <div class="row">
        <div style="width:30%; margin-right:20px;">
          <q-card inline style="width:100%;background-color:#FFD751;">
            <q-card-title>
              Simple Example
              <span slot="subtitle">Total number</span>
              <q-icon slot="right" name="trending_up"  color="dark"/>
            </q-card-title>
            <q-card-main>
              <h1 style="weight:300;color:54;float:right;margin-top:-40px;color:#ffffff;" class="q-display-3">
                <count-to ref='example1' class='example1' :start-val=startVal1 :end-val='endVal1' :duration=3000></count-to>
              </h1>
            </q-card-main>
          </q-card>
        </div>
        <div style="width:68%;">
          <q-card inline style="width:100%;">
            <q-card-title>
              <span slot="subtitle">Code</span>
              <q-icon slot="right" name="code"  color="dark"/>
            </q-card-title>
            <q-card-main>
              <code>&lt;count-to :startVal=&#x27;0&#x27; :endVal=&#x27;2017&#x27; :duration=3000&gt;&lt;/count-to&gt;</code>
              <br>
            </q-card-main>
            <q-card-separator />
            <q-card-actions>
              <q-btn flat round dense icon="timer" />
              <q-btn flat @click='start1' label="Start" />
              <q-btn flat @click='changeExampleEndVal' label="Change end-val" />
              <q-btn flat @click='incrementalUpdate' label="Incremental update" />
            </q-card-actions>
          </q-card>
        </div>
      </div>
      <br>
      <div class="row">
        <div style="width:30%; margin-right:20px;">
          <q-card inline style="width:100%;background-color:#FFD751;">
            <q-card-title>
              Count down Example
              <span slot="subtitle">Total number</span>
              <q-icon slot="right" name="arrow_downward"  color="dark"/>
            </q-card-title>
            <q-card-main>
              <h1 style="weight:300;color:54;float:right;margin-top:-40px;color:#ffffff;" class="q-display-3">
                <count-to ref='example2' class='example2' :start-val='2017' :end-val=0 :duration=3000></count-to>
              </h1>
            </q-card-main>
          </q-card>
        </div>
        <div style="width:68%;">
          <q-card inline style="width:100%;">
            <q-card-title>
              <span slot="subtitle">Code</span>
              <q-icon slot="right" name="code"  color="dark"/>
            </q-card-title>
            <q-card-main>
              <code> &lt;count-to :startVal=&#x27;2017&#x27; :endVal=&#x27;0&#x27; :duration=3000&gt;&lt;/count-to&gt;</code>
              <br>
            </q-card-main>
            <q-card-separator />
            <q-card-actions>
              <q-btn flat round dense icon="timer" />
              <q-btn flat @click='start2' label="Start" />
            </q-card-actions>
          </q-card>
        </div>
      </div>
      <br>
      <div class="row">
        <div style="width:30%; margin-right:20px;">
          <q-card inline style="width:100%;background-color:#FFD751;">
            <q-card-title>
              Custom Example
              <span slot="subtitle">Total number</span>
              <q-icon slot="right" name="monetization_on"  color="dark"/>
            </q-card-title>
            <q-card-main>
              <h1 style="weight:300;color:54;float:right;margin-top:-40px;color:#ffffff;" class="q-display-3">
                <count-to ref='example3' class='example3' :start-val='_startVal' :end-val='_endVal' :duration='_duration' :decimals='_decimals'
                  :separator='_separator' :prefix='_prefix' :suffix='_suffix' :autoplay=true>
                </count-to>
              </h1>
            </q-card-main>
          </q-card>
        </div>
        <div style="width:68%;">
          <q-card inline style="width:100%;">
            <q-card-title>
              <span slot="subtitle">Code</span>
              <q-icon slot="right" name="code"  color="dark"/>
            </q-card-title>
            <q-card-main>
              <div class="row">
                <code>&lt;count-to  :start-val=&#x27;{{_startVal}}&#x27; :end-val=&#x27;{{_endVal}}&#x27; :duration=&#x27;{{_duration}}&#x27; :decimals=&#x27;{{_decimals}}&#x27;
                  :separator=&#x27;{{_separator}}&#x27; :prefix=&#x27;{{_prefix}}&#x27; :suffix=&#x27;{{_suffix}}&#x27; :autoplay=false&gt;</code>
              </div>

              <div class="row">
                <q-input v-model.number='setStartVal' float-label="startVal" style="margin-right:5px;"/>
                <q-input v-model.number='setEndVal' float-label="endVal" style="margin-right:5px;" />
                <q-input v-model.number='setDuration' float-label="durationInput" style="margin-right:5px;" />
              </div>
              <div class="row">
                <q-input v-model.number='setDecimals' float-label="Decimals Input" style="margin-right:5px;" />
                <q-input v-model='setSeparator' float-label="Separator Input" style="margin-right:5px;" />
                <q-input v-model='setPrefix' float-label="Prefix Input" style="margin-right:5px;" />
                <q-input v-model='setSuffix' float-label="Suffix Input" style="margin-right:5px;" />
              </div>
              <br>
            </q-card-main>
            <q-card-separator />
            <q-card-actions>
              <q-btn flat round dense icon="timer" />
              <q-btn flat @click='start3' label="Start" />
              <q-btn flat @click='pauseResume' label="Pause/Resume" />
            </q-card-actions>
          </q-card>
        </div>
      </div>
    </div>
  </q-page>
</template>

<style>
</style>

<script>
import countTo from 'vue-count-to'

export default {
  name: 'PageHome',
  components: { countTo },
  data () {
    return {
      setStartVal: 0,
      setEndVal: 2017,
      setDuration: 3000,
      setDecimals: 0,
      setSeparator: ',',
      setSuffix: ' rmb',
      setPrefix: '¥ ',
      startVal1: 0,
      endVal1: 2017
    }
  },
  computed: {
    _startVal () {
      if (this.setStartVal) {
        return this.setStartVal
      } else {
        return 0
      }
    },
    _endVal () {
      if (this.setEndVal) {
        return this.setEndVal
      } else {
        return 0
      }
    },
    _duration () {
      if (this.setDuration) {
        return this.setDuration
      } else {
        return 100
      }
    },
    _decimals () {
      if (this.setDecimals) {
        if (this.setDecimals < 0 || this.setDecimals > 20) {
          alert('digits argument must be between 0 and 20')
          return 0
        }
        return this.setDecimals
      } else {
        return 0
      }
    },
    _separator () {
      return this.setSeparator
    },
    _suffix () {
      return this.setSuffix
    },
    _prefix () {
      return this.setPrefix
    }
  },
  methods: {
    changeExampleEndVal () {
      this.endVal1 = this.endVal1 + 1000
    },
    incrementalUpdate () {
      this.startVal1 = this.endVal1
      this.endVal1 = this.endVal1 + 1000
    },
    callback () {
      console.log('callback')
    },
    start1 () {
      this.$refs.example1.start()
    },
    start2 () {
      this.$refs.example2.start()
    },
    start3 () {
      this.$refs.example3.start()
    },
    pauseResume () {
      this.$refs.example3.pauseResume()
    }
  }
}
</script>
