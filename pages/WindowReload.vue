<template>
  <v-card>
    <v-card-title>Window Reload</v-card-title>
  </v-card>
</template>

<script>
export default {
  name: 'WindowReload',
  mounted() {
    this.pageReload()
  },
  methods: {
    pageReload() {
      if (window.name !== 'reloaded') {
        alert('Window Reload!!')
        window.name = 'reloaded'
        location.reload()
      } else {
        window.name = ''
      }
    },
  },
}
</script>
