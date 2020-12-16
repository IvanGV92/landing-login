<template>
  <div> 
        <!-- <section> 
            <div class="container mt-5">
                <div class="row">
                    <div class="col-md-12">
                        <ul class="list-group">
                            <li class="list-group-item">Name : {{ user.name }}</li>
                            <li class="list-group-item">Email : {{ user.email }}</li>
                        </ul> 
                    </div>
                </div>
            </div>
        </section> -->
    <header class="header-container">
     <header-page></header-page>
    </header>
    
    <carousel></carousel>
    
     <div class="section">
        <a name="Sec-noticias"></a>
        <h2>
            NOTICIAS
        </h2>
    </div>

    <div class="container">
      <section-api></section-api>
    </div> 

    <div class="section">
        <h2>
            EQUIPO
        </h2>
        <a name="Sec-equipo"></a>
    </div>
    <div class="container">
      <div class="row row-cols-1 row-cols-md-3 g-4">
        <team-card
          v-bind:member="item"
          v-for="(item, index) of team"
          :key="index"
        ></team-card>
      </div>
    </div>
    
    <page-footer></page-footer>
  </div>    
</template>

<script>
import VueJwtDecode from "vue-jwt-decode";
import PageFooter from "./PageFooter.vue";
import HeaderPage from './HeaderPage.vue';
import Carousel from './Carousel.vue';
import SectionApi from './SectionApi.vue';
import TeamCard from './TeamCard.vue';
export default {
    components: {
        HeaderPage,
        Carousel,
        PageFooter,
        SectionApi,
        TeamCard
      
    },
    data() { 
        return { 
            team: [
                    {
                    codigo: 1,
                    nombre: "Alexander Montenegro",
                    rol: "Desarrollador Frontend",
                    descripcion:
                        "Soy tecnologo en sistemas, egresado de la Escuela Colombiana de Carreras Industriales.",
                    imagen: "./ALEXM-2020.jpg",
                    },
                    {
                    codigo: 2,
                    nombre: "Ivan Gonzalez",
                    rol: "Desarrollador Frontend",
                    descripcion:
                        "Soy ingeniero de sistemas con especializacion en gerencia de proyectos.",
                    imagen: "./FOTO-IVAN.jpg",
                    },
                    {
                    codigo: 3,
                    nombre: "Manuel Sanchez",
                    rol: "Desarrollador Backend",
                    descripcion:
                        "Soy tecnologo en sistemas, egresado de la Escuela Colombiana de Carreras Industriales.",
                    imagen: "./FOTO-MANUEL-S.jpg",
                    },
      ],
            user: {} 
                };
                },
    methods: { 
        getUserDetails() { 
            let token = localStorage.getItem("jwt"); 
            let decoded = VueJwtDecode.decode(token); 
            console.log('hola decode',decoded); 
            this.user = decoded; 
            },
       
            },
        created() { 
            this.getUserDetails();
        }
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
