<template>
  <div>
    <div class="ui fixed inverted menu vue-color">
      <div class="ui container">
        <a href="/" class="header item">Dokter</a>
      </div>
    </div>
    <div class="row">
      <form @submit.prevent="save" class="ui form" name="dokter">
        <h5>Tambah data dokter</h5>
        <div class="col-sm margin">
          <div class="label">
            <label>name</label>
            <input type="text" name="nama" v-model="form.nama" />
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
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "MyForm",
  data() {
    return {
      form: {
        user_id: "",
        nama: "",
        keahlian: "",
      },
    };
  },
  methods: {
    async get(a) {
      let data = axios.get("http://localhost:3000/users/" + a);
      let b = data.data.values;
      this.form.nama = b.nama;
      this.form.keahlian = b.keahlian;
    },
    async save() {
      const x = new URLSearchParams(window.location.search);
      for (const param of x) {
        this.user_id = param["1"];
      }
      if (this.user_id == "") {
        this.add();
      } else {
        this.edit();
      }
    },
    async add() {
      await axios
        .post("http://localhost:3000/users/", this.form)
        .then((res) => {
          (this.form.nama = ""), (this.form.keahlian = "");
          alert(JSON.stringify(res.data.values));
          // alert("Tekan tombol Dokter untuk kembali ke HOME!");
          if (confirm("Balik ke HOME?") == true) {
            this.$router.push("/");
            return true;
          } else {
            this.$router.push("/tambah");
            return false;
          }
        })
        .catch((err) => {
          console.log(err);
        });
    },
    async edit() {
      let a;
      const params = new URLSearchParams(window.location.search);
      for (const param of params) {
        a = param["1"];
      }
      this.form.user_id = a;
      await axios
        .put("http://localhost:3000/users/", this.form)
        .then((res) => {
          alert(JSON.stringify(res.data.values));
          // alert("Tekan tombol Dokter untuk kembali ke HOME!");
          if (confirm("Balik ke HOME?") == true) {
            this.$router.push("/");
            return true;
          } else {
            this.$router.push("/tambah");
            return false;
          }
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style scoped>
.margin {
  width: 70%;
  margin: 25px;
  text-align: center;
}
.label {
  text-align: left;
  font-weight: bold;
}
</style>
