<template>
  <div class="customer-list">
      <div class="data">
          <table class="ui celled table">
              <thead>
                  <tr>
                      <th style="width: 50px; text-align: center;">#</th>
                      <th>Name</th>
                      <th>Keahlian</th>
                      <th style="width: 148px;">Action</th>
                  </tr>
              </thead>
              <tbody>
                  <Customer v-for="dokter in dokters"
                  :key="dokter.id"
                  :dokter="dokter"
                  />
              </tbody>
          </table>
      </div>
  </div>
</template>

<script>
import Customer from "./Customer"
export default {
    name: "CustomerList",
    components: {
        Customer
    },
    props: {
        dokter: {
            type: Array
        }
    }
};
</script>

<style scoped>

</style>
