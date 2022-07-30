<template>
  <div style="background-color: #ececec; padding: 20px">
    <a-row :gutter="16">
      <a-col v-for="post in listado" :key="post.id"  span="8">
        <a-card :title="post.title" :bordered="true">
          <a-msj :mensaje ="post.body"></a-msj>
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