<template>
  <div>
    <a-card v-for="todos in listado" :key="todos.id" :title="'N° '+todos.id" style="width: 300px">
      <p>{{ todos.title}}</p>
      <p>{{todos.completed}}</p>
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