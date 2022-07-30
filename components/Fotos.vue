<template>
  <div style="background-color: #ececec; padding: 20px">
    <a-row :gutter="16">
      <a-col v-for="fotos in listado" :key="fotos.id" span="8">
        <a-card hoverable style="width: 240px">
          <template #cover>
            <img alt="example" :src="fotos.url" />
          </template>
          <a-card-meta :title="fotos.title">
            <template #description>{{fotos.description}}</template>
          </a-card-meta>
        </a-card>
      </a-col>
    </a-row>
  </div>
</template>

<script>
  export default {
    data: ()  => ({
      listado: [
        {
          name: "Imagen1",
          url: "https://os.alipayobjects.com/rmsportal/QBnOOoLaAfKPirc.png",
          description: "www.instagram.com"
        }
      ]
    }),

    async fetch() {
      const data = await this.$axios.$get("https://jsonplaceholder.typicode.com/photos")
      this.listado = data
    }
  }
</script>