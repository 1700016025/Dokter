<template>
  <div class="my-form">
      <form-class="ui form">
        <div class="fields">
        <div class="four wide field">
            <label>name</label>
            <input type="text" name="name" placeholder="name" />
        </div>

        <div class="six wide field">
            <label>keahlian</label>
            <input type="text" name="keahlian" placeholder="keahlian" />
        </div>

        <div class="two wide field">
            <button class="ui primary button submit-button">Save</button>

        </div>
    </div>
      </form>
  </div>
</template>

<script>
export default {
    name: "MyForm"
};
</script>

<style scoped>

</style>
