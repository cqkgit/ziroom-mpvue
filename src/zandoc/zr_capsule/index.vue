<template>
  <div class="container">

    <div class="doc-title zr-hairline--bottom">CAPSULE</div>

    <div class="zr-panel-title">基本用法</div>
    <div class="zr-panel">
      <div class="zr-cell zr-cell--last-child">
        <capsule v-bind="{leftText:'1折', rightText:'限购一份'}" ></capsule>
        <capsule v-bind="{leftText:'1折', rightText:'限购一份', type:'danger'}" ></capsule>
      </div>
    </div>

    <div class="zr-panel-title">自定义颜色</div>
    <div  class="zr-panel">
      <div class="zr-cell zr-cell--last-child">
        <capsule v-bind="data" ></capsule>
      </div>
    </div>
  </div>
</template>

<script>
  import capsule from '../../components/zan/capsule'

  export default {
    components: {
      capsule
    },
    data () {
      return {
        data: {
          leftText: '1折',
          rightText: '限购一份',
          color: '#38f',
          onclick: null
        }
      }
    },
    mounted () {
      this.data.onclick = this.change
    },
    methods: {
      change () {
        this.data.color = Math.random() > 0.5 ? '#7f71ff' : '#ff6c2e'
      }
    }
  }
</script>
<style >
</style>
<style  scoped>
  .zr-capsule + .zr-capsule {
    margin-left: 10px;
  }
</style>
