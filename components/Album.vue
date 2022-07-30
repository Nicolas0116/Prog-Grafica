<template>
  <div>
    <a-card v-for="album in listado" :key="album.id" :title="'Album N°'+album.id">
      <a-card-grid :style="album.title"></a-card-grid>
      </a-card>
    </div>
</template>

<script>
  export default {
    data: ()  => ({
      listado: [{}]
    }),

    async fetch() {
      const data = await this.$axios.$get("https://jsonplaceholder.typicode.com/albums")
      this.listado = data
    }
  }
</script>