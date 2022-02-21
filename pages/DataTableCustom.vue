<template>
  <v-card>
    <v-card-title>データテーブルグループ化カスタマイズ</v-card-title>
    <v-data-table :items='items' :headers='headers' show-group-by group-by='group'>
      <template #[`group.header`]="{ group, items, headers, toggle, isOpen, remove }">
        <td>
          <v-btn @click="toggle" x-small icon :ref="group">
            <v-icon v-if="isOpen">mdi-minus</v-icon>
            <v-icon v-else>mdi-plus</v-icon>
          </v-btn>
          {{ group }}
          <v-btn @click='remove' x-small icon :ref='group'>
            <v-icon>mdi-close</v-icon>
          </v-btn>
        </td>
        <td>小計：{{ getTotal(items) }}</td>
        <td :colspan="headers.length-2"></td>
      </template>
      <template #[`group.summary`]="{ items, headers }">
        <td>小計：{{ getTotal(items) }}</td>
        <td :colspan="headers.length-1"></td>
      </template>
    </v-data-table>
  </v-card>
</template>

<script>
export default {
  name: 'DataTableCustom',
  data() {
    return {
      items: [
        { id: '1', name: '牛乳', value: 10, group: 'グループ１' },
        { id: '2', name: 'チーズ', value: 20, group: 'グループ２' },
        { id: '3', name: 'ヨーグルト', value: 30, group: 'グループ３' },
        { id: '4', name: 'バター', value: 40, group: 'グループ３' },
        { id: '5', name: '練乳', value: 50, group: 'グループ３' },
        { id: '6', name: 'クリーム', value: 60, group: 'グループ２' },
        { id: '7', name: 'アイスクリーム', value: 70, group: 'グループ２' },
        { id: '8', name: '脱脂粉乳', value: 80, group: 'グループ１' },
        { id: '9', name: '乳酸菌飲料', value: 90, group: 'グループ１' },
        { id: '10', name: 'ホエイプロテイン', value: 100, group: 'グループ１' },
      ],
      headers: [
        { text: 'ID', value: 'id', groupable: false },
        { text: '名称', value: 'name', groupable: false },
        { text: '値', value: 'value', groupable: false },
        { text: 'グループ', value: 'group' },
      ]
    }
  },
  methods: {
    getTotal(items) {
      let total = 0
      total = items.reduce((prev, current) => {
        return prev + current.value
      }, 0)
      return total
    }
  }
}
</script>
