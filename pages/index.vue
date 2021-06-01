<template>
  <div class="container">
    <section>
      <q-table
        class="basic-table"
        title="COVID-19 台灣疫情報告"
        :data="data"
        :columns="columns"
        row-key="name"
      />
    </section>
  </div>
</template>

<script>
import jsonData from '~/static/Age_County_Gender_19Cov.json'
export default {
  name: 'index',
  data () {
    return {
      jsonData,
      columns: [
        {
          name: 'Treats',
          required: true,
          label: '發病年份',
          align: 'left',
          field: row => row['發病年份'],
          format: val => `${val}`,
          sortable: true
        },
        { name: 'calories', align: 'center', label: '發病月份', field: '發病月份', sortable: true },
        { name: 'fat', label: '縣市', field: '縣市', sortable: true },
        { name: 'carbs', label: '鄉鎮', field: '鄉鎮' },
        { name: 'protein', label: '性別', field: '性別' },
        { name: 'sodium', label: '是否為境外移入', field: '是否為境外移入' },
        { name: 'calcium', label: '年齡層', field: '年齡層', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
        { name: 'iron', label: '確定病例數', field: '確定病例數', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) }
      ],
      data: jsonData
    }
  },
  computed: {
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
}
</style>
