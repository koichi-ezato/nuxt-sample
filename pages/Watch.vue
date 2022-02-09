<template>
  <v-card>
    <v-card-title>値を監視する</v-card-title>
    <v-card-text>
      <v-text-field v-model='watchData' label='監視対象データ' />
    </v-card-text>
    <v-card-text>
      <p>新しい値：{{ newWatchData }}</p>
      <p>古い値：{{ oldWatchData }}</p>
    </v-card-text>
    <v-card-title>オブジェクトの値も監視する</v-card-title>
    <v-card-text>
      <v-text-field v-model='arrayObj.value' label='監視対象データ' />
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'WatchPage',
  data() {
    return {
      watchData: '1',
      newWatchData: '',
      oldWatchData: '',
      arrayObj: { value: '10', },
      arrayNewWatchData: '',
      arrayOldWatchData: '',
    }
  },
  watch: {
    watchData(newValue, oldValue) {
      this.newWatchData = newValue
      this.oldWatchData = oldValue
    },
    // オブジェクトの要素も監視可能です
    arrayObj: {
      handler() {
        alert('変更を検知しました。変更された値：' + this.arrayObj.value)
      },
      deep: true
    },
  }
}
</script>
