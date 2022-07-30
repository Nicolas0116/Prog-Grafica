<template>
  <div>
  <a-descriptions v-for="usuario in listado" :key="usuario.id"  :title="'User: '+usuario.username">
      <a-descriptions-item :label="'Nombre: '+usuario.name"></a-descriptions-item>
      <a-descriptions-item :label="'Tel.: '+ usuario.phone"></a-descriptions-item>
      <a-descriptions-item :label="'Ciudad: '+ usuario.address.city"></a-descriptions-item>
      <a-descriptions-item :label="'Correo: '+usuario.email"></a-descriptions-item>
      <a-descriptions-item :label="'Empresa: '+ usuario.company.name"></a-descriptions-item>
      <a-descriptions-item :label="'Sitio Web: '+ usuario.website"></a-descriptions-item>
    </a-descriptions>
  </div>
</template>



<script>
  export default {
    data: ()  => ({
      listado: [{}]
    }),

    async fetch() {
      const data = await this.$axios.$get("https://jsonplaceholder.typicode.com/users")
      this.listado = data
    }
  }
</script>