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
          <tr v-for="(dokter, index) in dokters" :key="index">
            <td>{{ dokter.id }}</td>
            <td>{{ dokter.nama }}</td>
            <td>{{ dokter.keahlian }}</td>
            <td>
              <button
                class="mini ui blue button"
                v-on:click="editDokter(dokter.id)"
              >
                Edit
              </button>
              <button class="mini ui red button" @click="deleteDkter(dokter.id)">Hapus</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      dokters: [],
    };
  },
  mounted() {
    this.getDokter();
  },
  methods: {
    async getDokter() {
      let smtr = await axios.get("http://localhost:3000/users");
      this.dokters = smtr.data.values;
    },
    async deleteDkter(a){
        await axios.delete("http://localhost:3000/users/", {data: {user_id:a}})
        .then((result) => {
            alert(JSON.stringify(result.data.values));
            this.getDokter()
        }).catch((err) => {
            console.log(err);
        });
    },
    async editDokter(a){
      location.replace('/tambah'+'?id='+a)
    }
  },
};
</script>

<style scoped></style>
