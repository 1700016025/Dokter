<template>
  <div id="app">
    <div class="ui fixed inverted menu vue-color">
      <div class="ui container">
        <a href="#" class="header item">Dokter</a>
      </div>
    </div>

    <div class="ui main container">
      <!-- <MyForm :name="nama" :keahlian="keahlian" /> -->
      <Customer v-for="dokter in dokters" :key="dokter.id" :dokter="dokter" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
// import MyForm from "./components/MyFrom";
import Customer from "./components/Customer";

export default {
  name: "App",
  components: {
    // MyForm,
    Customer,
  },
  data() {
    return {
      dokters: [],
    };
  },
  created() {
    this.getDokter();
  },
  methods: {
    async getDokter() {
      let smtr = await axios.get("http://localhost:3000/users");
      this.dokters = smtr.data.values;
    },
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
