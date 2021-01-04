<template>
<v-carousel hide-delimiters  cycle show-arrows-on-hover>
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel>
</template>


<script>
export default {
    name: "Carausel",
     data()  {
      return{
      items:[
        {src: "https://idsb.tmgrup.com.tr/ly/uploads/images/2020/08/21/53276.jpeg"},
        {src: "https://www.mintic.gov.co/portal/604/articles-159504_foto_marquesina.jpg"},
        {src: "https://ikiwi.co/wp-content/uploads/Radar-Fintech-Colombia-2020-1024x576.jpeg"}

      ]
    }}
}
</script>

