<template>
    <div>
        <button @click="seleccionarFavorito()">
            Seleccionar Favorito
        </button>
        <button @click="eliminarComic()" class="rojo">
            Eliminar comic
        </button>
        <h2 style="color:blue">{{comic.titulo}}</h2>
        <h3>{{ comic.descripcion }}</h3>
        <h3 :class="{
            rojo: comic.year <= 2000,
            verde: comic.year > 2000
        }">
            {{ comic.year }}
        </h3>
        <img :src="comic.imagen" :title="comic.titulo"/>
    </div>
</template>

<script>
    export default {
        name: "HijoComic",
        props: ["comic", "index"],
        methods: {
            eliminarComic(){
                this.$emit("eliminarComic", this.index);
            },
            seleccionarFavorito() {
                //METODO PARA LLAMAR AL PADRE Y ENVIAR NUESTRO COMIC
                this.$emit("seleccionarFavorito", this.comic);
            }
        }
    }
</script>

<style scoped>
    @import './../assets/css/estilocomic.css';
</style>
