<template>
  <span>送信された値：{{ message }}</span>
</template>

<script>
export default {
  name: 'EventBusReceive',
  data() {
    return {
      message: '',
    }
  },
  mounted() {
    this.$nuxt.$on('SEND_MESSAGE', (result) => {
      this.message = result
    })
  },
  beforeDestroy() {
    this.$nuxt.$off('SEND_MESSAGE')
  },
}
</script>
