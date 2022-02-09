<template>
  <v-card>
    <v-card-title>EventBusサンプル</v-card-title>
    <v-card-text>
      <event-bus-receive />
    </v-card-text>
    <v-card-actions>
      <event-bus-send />
    </v-card-actions>
  </v-card>
</template>

<script>
import EventBusReceive from '~/components/EventBusReceive'
import EventBusSend from '~/components/EventBusSend'

export default {
  name: 'EventBus',
  components: { EventBusSend, EventBusReceive }
}
</script>
