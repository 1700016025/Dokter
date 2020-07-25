<template>
  <div id="app">
      <div class="ui fixed inverted menu vue-color">
        <div class="ui container">
          <a href="#" class="header item">Dokter</a>
        </div>
     </div>

     <div class="ui main container">
       <MyForm />
     </div>
  </div>
</template>

<script>
import MyForm from "./components/MyFrom";

export default {
  name: "App",
  components: {
    MyForm    
  }
}
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
