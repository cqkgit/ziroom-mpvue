<template>
  <div class="container">

    <div class="doc-title zr-hairline--bottom">TOAST</div>

    <div class="zr-btns" style="margin-top: 15vh;">
      <button class="zr-btn" @click="showToast">
        显示toast
      </button>

      <button class="zr-btn" @click="showIconToast">
        显示 Icon 图标的toast
      </button>

      <button class="zr-btn" @click="showImageToast">
        自定义图片作为图标的toast
      </button>

      <button class="zr-btn" @click="showLoadingToast">
        显示 Loading toast
      </button>

      <button class="zr-btn" @click="showOnlyIcon">
        只显示图标的toast
      </button>

      <button class="zr-btn" @click="showLoading">
        显示 Loading
      </button>
    </div>

    <_toast />
  </div>
</template>

<script>
  import { getComponentByTag } from '../../utils/helper'
  import ZrToast from '../../components/zan/toast'
  export default {
    components: {
      _toast: ZrToast
    },
    data  () {
      return {
      }
    },
    mounted () {
      this.toast = getComponentByTag(this, '_toast')
    },
    methods: {
      showToast () {
        this.toast.showZrToast('toast的内容')
      },

      showIconToast () {
        this.toast.showZrToast({
          title: 'toast的内容',
          icon: 'fail'
        })
      },

      showImageToast () {
        this.toast.showZrToast({
          title: 'toast的内容',
          image: 'https://b.yzcdn.cn/v2/image/dashboard/secured_transaction/suc_green@2x.png'
        })
      },

      showLoadingToast () {
        this.toast.showZrToast({
          title: 'toast的内容',
          icon: 'loading'
        })
      },

      showOnlyIcon () {
        this.toast.showZrToast({
          icon: 'fail'
        })
      },

      showLoading () {
        this.toast.showZrLoading('加载中')
      }
    }
  }
</script>
<style  scoped >
</style>
