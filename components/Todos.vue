<template>
  <div>
    <a-card v-for="todos in listado" :key="todos.Id" :title="'N°'+todos.userId" style="width: 300px">
      <template #extra><a href="#">more</a></template>
      <p>{{ todos.title}}</p>
      <a-title :completed="todos.completed"></a-title>
    </a-card>
  </div>
</template>

<script>
  export default {
    data: ()  => ({
      listado: [{}]
    }),

    async fetch() {
      const data = await this.$axios.$get("https://jsonplaceholder.typicode.com/todos")
      this.listado = data
    }
  }
</script>