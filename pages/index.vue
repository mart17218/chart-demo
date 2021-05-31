<template>
  <div class="container">
    <section>
      <table>
        <thead></thead>
        <tbody>
          <tr v-for="(data, index) in jsonData" :key="index">
            <td v-for="(thead, tIndex) in TABLE_HEAD" :key="tIndex">
              {{ data[thead] }}
            </td>
          </tr>
        </tbody>
      </table>
    </section>
  </div>
</template>

<script>
import jsonData from '~/static/Age_County_Gender_19Cov.json'
export default {
  name: 'index',
  data () {
    return {
      jsonData
    }
  },
  computed: {
    TABLE_HEAD () {
      const keyName = this.jsonData[0]
      delete keyName['確定病名']
      return Object.keys(keyName)
    }
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
