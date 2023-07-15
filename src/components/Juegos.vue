<template>
    <div id="juegos">
        <h2 class="text-white text-center tituloJuegos mb-4">Lista de Juegos</h2>
        <div id="flexPadre" class="d-flex flex-wrap justify-content-center mt-3">
            <div class="card m-1" v-for="(juego, index) in juegos" v-bind:key="index" style="width: 18rem;">
                <div class="contenedorImagen">
                    <img v-bind:src="juego.background_image" class="card-img" alt="...">
                </div>
                

                <div class="card-body">
                    <h5 class="card-title">{{ juego.name }}</h5>
                    <p class="card-text">Esrb Rating: {{ juego.esrb_rating.name }}</p>
                </div>

                <ul class="list-group list-group-flush">
                    <li class="list-group-item">Rating: {{ juego.rating }}</li>
                    <li class="list-group-item">Released: {{ juego.released }}</li>
                    <li class="list-group-item">Updated: {{ juego.updated }}</li>
                </ul>

                <div class="card-body">
                    <a v-on:click.prevent="mostrarOpiniones(juego.name)" href="#" class="btn btn-propio">
                        <i class="fi fi-sr-comment-alt-dots"></i>
                        Comenta
                    </a>
                    <a v-on:click="irAdministracion(juego.name)" class="btn btn-like">
                        <i class="fi fi-sr-heart iconoTamaño"></i>
                    </a>
                </div>

            </div>
        </div>
    </div>


</template>

<script>
    import axios from 'axios';
    export default{
        name: 'juegos',
        data: function(){
            return{
               cantidadJuegos: 0,
               juegos: []
            }
        },
        methods:{
            consumirApi: function(){
                let url = 'https://api.rawg.io/api/games?key=548ac8fcc5ad4b3780b81ed0b0a992c6';
                axios(url)
                .then(respuesta =>{
                    console.log(respuesta)
                    console.log(respuesta.data.results[9].name)
                    this.cantidadJuegos = respuesta.data.results.length
                    //logica para acumular en el areglo 'juegos' cada juego de las distintas paginas
                    for(let i = 0; i < this.cantidadJuegos; i++){
                        this.juegos.push(respuesta.data.results[i])
                    }
                })
                .catch(error => {
                    console.log(error)
                })
            },
            mostrarOpiniones: function(nombreJuego){
                this.$router.push(`/opiniones/${nombreJuego}`)
            },
            irAdministracion:function(nombreJuego){
                this.$router.push(`/administracion/${nombreJuego}`);
            },
        },
        created(){
            this.consumirApi();
        }
    }

</script>

<style scoped>
    .contenedorImagen{
        display: flex;
        height: 180px;
    }

    .btn-propio{
        background-color: rgb(15, 36, 221);
        color: rgba(255, 255, 255, 0.932);
    }
    .iconoTamaño{
        color: red;
        font-size: 27px;
    }
    .btn-like{
        background-color: azure;
    }
    .tituloJuegos{
       
        font-size: 2.4rem;
  font-weight: bold;
  font-family: 'Press Start 2P', cursive;
  color: #8a1cd4; /* Color de texto en tono púrpura */
  text-shadow: 4px 4px 0px #000, 6px 6px 0px #8a1cd4; /* Efecto 4D sobresaliente */
    }
</style>