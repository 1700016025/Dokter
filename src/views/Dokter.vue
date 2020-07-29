<template>
  <div id="app">
    <div class="ui fixed inverted menu vue-color">
      <div class="ui container">
        <a href="/" class="header item">Dokter</a>
      </div>
    </div>

    <div class="ui main container">
      <!-- <MyForm :name="nama" :keahlian="keahlian" /> -->
      <button class="ui primary button" style="float:left; margin:10px;" @click="$router.push('/tambah')">
          Tambah Dokter
        </button>
      <Customer />
    </div>
  </div>
</template>

<script>
import Customer from "../components/Customer";

export default {
  name: "App",
  components: {
    Customer,
  },
};
</script>

<style>
.vue-color {
  background: #41b883 !important;
}

.main.container {
  margin-top: 60px;
}

.submit-button {
  margin-top: 24px !important;
  float: right;
}
</style>
