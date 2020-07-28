<template>
      <tr>
        <td>{{ customer.id }}</td>
        <td>{{ customer.name }}</td>
        <td>{{ customer.keahlian }}</td>
        <td>
        <button class="mini ui blue button">Edit</button>
         <button class="mini ui red button">Hapus</button>
        </td>
    </tr>
    
</template>

<script>
export default {
    name: "Customer",
    props: {
        customer: {
            type:Object
        }
    }
};
</script>

<style scoped>

</style>
