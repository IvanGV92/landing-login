<template>
  <div class="row row-cols-1 row-cols-md-2">
    <div v-for="(noticia, index) of noticias" :key="index" class="col mb-4">
      <div class="card">
        <img :src="noticia.urlToImage" class="card-img-top" alt="Noticia" />
        <div class="card-body">
          <h5 class="card-title">{{ noticia.title }}</h5>
          <p class="card-text">{{ noticia.description }}</p>
        </div>
        <button
          type="button"
          class="btn btn-info"
          v-on:click="redirectToPage(noticia.url)"
        >
          Ver más
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
const API_KEY = "fedd8f06e8034e2082bd88cdbae03bb1";
export default {
  name: "SectionsApi",
  data() {
    return {
      noticias: null,
    };
  },
  methods: {
    redirectToPage(urlSite) {
      window.open(urlSite, "_blank");
    },
  },

  mounted() {
    axios
      .get(`http://newsapi.org/v2/top-headlines?country=co&apiKey=${API_KEY}`)
      .then((response) => {
        this.noticias = response.data.articles.slice(0, 4);
      });
  },
};
</script>

<style lang="stylus" scoped></style>