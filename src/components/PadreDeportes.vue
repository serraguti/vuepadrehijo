<template>
    <div>
        <h1>Padre deportes</h1>
        <h1 style="color:red" v-if="favorito">
            {{favorito}}
        </h1>
        <ul>
            <li v-for="depor in deportes" :key="depor">
                <HijoDeporte :nombredeporte="depor"
                v-on:seleccionarFavoritoParent="seleccionarFavoritoParent"/>
            </li>
        </ul>
    </div>
</template>

<script>
import HijoDeporte from './HijoDeporte.vue';

    export default {
        name: "PadreDeportes",
        components: {
            HijoDeporte
        },
        methods: {
            seleccionarFavoritoParent(nombre) {
                this.favorito = nombre;
            },
            crearAlgoNuevo() {
                this.deportes.push("Algo nuevo");
            }
        },
        data() {
            return {
                deportes: ["Surf", "Curling", "Padel", "Futbol", "Peonza"],
                favorito: null
            }
        }
    }
</script>