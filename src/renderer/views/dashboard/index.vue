<template>
  <div class="dashboard-container">
    <panel-group @handleSetLineChartData="handleSetLineChartData" />
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import PanelGroup from '../../../renderer/components/PanelGroup'
// import { LineChart } from '../../../renderer/components/LineChart'

const lineChartData = {
  newVisitis: {
    expectedData: [100, 120, 161, 134, 105, 160, 165],
    actualData: [120, 82, 91, 154, 162, 140, 145]
  },
  messages: {
    expectedData: [200, 192, 120, 144, 160, 130, 140],
    actualData: [180, 160, 151, 106, 145, 150, 130]
  },
  purchases: {
    expectedData: [80, 100, 121, 104, 105, 90, 100],
    actualData: [120, 90, 100, 138, 142, 130, 130]
  },
  shoppings: {
    expectedData: [130, 140, 141, 142, 145, 150, 160],
    actualData: [120, 82, 91, 154, 162, 140, 130]
  }
}

export default {
  name: 'dashboard',
  computed: {
    ...mapGetters(['name', 'roles'])
  },
  components: {
    PanelGroup
    //    LineChart
  },
  data() {
    return {
      lineChartData: lineChartData.newVisitis
    }
  },
  methods: {
    handleSetLineChartData(type) {
      this.lineChartData = lineChartData[type]
    }
  }
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}

.title-bar{
    position: relative;
    width: 100%;
    height: 50px;
}

.title-bar .borda{
    width:90%;
    position: absolute;
    height: 2px;
    background-color: #000;
    margin: auto;
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
}

.title{
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    margin: auto;
    width: 80px;
    height: 25px;
    background-color: #FFF;
    padding: 0px 20px;
}

.github-corner {
position: absolute;
top: 0px;
border: 0;
right: 0;
}

.chart-wrapper {
background: #fff;
padding: 16px 16px 0;
margin-bottom: 32px;
}
</style>
