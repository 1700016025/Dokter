<template>
  <div class="my-form">
      <form class="ui form">
        <div class="fields">
        <div class="four wide field">
            <label>name</label>
            <input type="text" name="name" v-model="name" />
        </div>

        <div class="six wide field">
            <label>keahlian</label>
            <input type="text" name="keahlian" v-model="keahlian" />
        </div>

        <div class="two wide field">
            <button class="ui primary button submit-button">Simpan</button>

        </div>
    </div>
      </form>
  </div>
</template>

<script>
export default {
    name: "MyForm",
    props: ['name', 'keahlian']
};
</script>

<style scoped>

</style>
