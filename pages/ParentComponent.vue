<template>
  <v-card>
    <v-card-title>親コンポーネント</v-card-title>
    <child-component ref='child' />
    <v-card-actions>
      <v-btn tile color='primary' @click='execChildComponent'>子コンポーネントのメソッド実行</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
import ChildComponent from '~/components/Child'

export default {
  name: 'ParentComponent',
  components: { ChildComponent },
  methods: {
    execChildComponent() {
      this.$refs.child.changeValue()
    }
  }
}
</script>
