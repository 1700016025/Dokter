<template>
  <div class="customer-list">
    <div class="data">
      <h5>Data Dokter</h5>
      <button class="mini ui blue button" @click="$router.push('/tambah')">Tambah Data</button>
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
          <tr>
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
              <button class="mini ui red button">Hapus</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import router from '../router/index'
export default {
  name: "dokter",
  components: {
  },
  props: {
    dokter: Object,
  },
  data() {
    return {
      nama: "",
      keahlian: "",
    };
  },
  methods: {
      tambah: () => {
          router.push('/tambah')
      }
  },
};
</script>

<style scoped></style>
