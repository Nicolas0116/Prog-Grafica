<template>
  <div style="background-color: #ececec; padding: 30px">
    <a-row :gutter="16">
      <a-col v-for="post in listado" :key="post.id"  span="12">
        <a-card :title="post.title" :bordered="true">
          <p>{{post.body}}</p>
        </a-card>
      </a-col>
    </a-row>
  </div>
</template>


<script>
  export default {
    data: ()  => ({
      listado: [{}]
    }),

    async fetch() {
      const data = await this.$axios.$get("https://jsonplaceholder.typicode.com/posts")
      this.listado = data
    }
  }
</script>