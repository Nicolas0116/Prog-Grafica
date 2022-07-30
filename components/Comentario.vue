<template>
  <div>
  <a-comment v-for="comentario in listado" :key="comentario.id">
    <template #author>{{comentario.email}}</template>
    <template #avatar>
      <a-avatar src="https://joeschmoe.io/api/v1/random" alt="Han Solo" />
    </template>
    <template #content>
      <p>{{comentario.name}}</p>
      <p>
        {{comentario.body}}
      </p>
    </template>
  </a-comment>
  </div>
</template>


<script>
  export default {
    data: ()  => ({
      listado: [{}]
    }),

    async fetch() {
      const data = await this.$axios.$get("https://jsonplaceholder.typicode.com/comments")
      this.listado = data
    }
  }
</script>