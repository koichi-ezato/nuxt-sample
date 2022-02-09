<template>
  <v-btn tile @click='sendMessage'>送信</v-btn>
</template>

<script>
export default {
  name: 'EventBusSend',
  methods: {
    sendMessage() {
      this.$nuxt.$emit('SEND_MESSAGE', 'メッセージを送信しました。')
    },
  },
}
</script>
