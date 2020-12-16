<template>
     
    <div>
        <nav class="navbar fixed-top navbar-expand-lg navbar-dark bg-primary">
            <a class="navbar-brand" href="#">Inicio</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item active">
                        <a class="nav-link" href="#Sec-noticias">Noticias<span class="sr-only">(current)</span></a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#Sec-equipo">Equipo</a>
                    </li>
                </ul>
                <div class="collapse navbar-collapse justify-content-end" id="navbarNav" > 
                        <ul class="navbar-nav">
                            <li class="nav-item active">
                                <a class="nav-link" @click="logUserOut"> Logout</a>
                            </li>
                        </ul> 
                    </div> 
            </div>
    
        </nav>
    </div>
    

</template>

<script>
export default {
    name: 'HeaderPage',
    methods: {
         logUserOut() { 
            localStorage.removeItem("jwt"); 
            this.$router.push("/"); 
            } 
    }
};
</script>

<style scoped>
   
</style>
