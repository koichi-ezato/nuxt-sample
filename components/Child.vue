<template>
  <v-card-text v-text='value' />
</template>

<script>
export default {
  name: 'ChildComponent',
  data() {
    return {
      value: '子コンポーネント',
    }
  },
  methods: {
    changeValue() {
      this.value = '子コンポーネントのメソッドが実行されました'
    }
  },
}
</script>
