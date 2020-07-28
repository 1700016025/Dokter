<template>
  <div class="row">
    <form @submit.prevent="add" class="ui form">
      <h5>Tambah data dokter</h5>
      <div class="col-sm margin">
        <div class="label">
          <label>name</label>
          <input type="text" name="name" v-model="form.nama" />
        </div>

        <div class="label">
          <label>keahlian</label>
          <input type="text" name="keahlian" v-model="form.keahlian" />
        </div>

        <div class="">
          <button class="ui primary button submit-button" type="submit">
            Simpan
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "MyForm",
  data() {
    return {
      form: {
        nama: "",
        keahlian: "",
      },
    };
  },
  methods: {
    add() {
      axios
        .post("http://localhost:3000/users/", this.form)
        .then((res) => {
          console.log(res);
          this.form.nama = "",
          this.form.keahlian = ""
          alert(JSON.stringify(res.data.values));
          this.$route.push('/');
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style scoped>
.margin{
    width: 70%;
    margin: 25px;
    text-align: center;
}
.label{
    text-align: left;
    font-weight: bold;
}
</style>
