<template>
    <div>
        <h1>Padre números</h1>
        <h1 style="color:red">
            La suma es {{suma}}
        </h1>
        <button style="background-color:red" @click="generarNumero">
            Nuevo NUMERO
        </button>        
        <div v-for="num in numeros" :key="num">
            <HijoNumero :numero="num"
            v-on:sumarNumeros="sumarNumeros"/>
        </div>
    </div>
</template>

<script>
import HijoNumero from './HijoNumero.vue';
    export default {
        name: "PadreNumeros",
        methods: {
            generarNumero() {
                var random = parseInt(Math.random() * 100) + 1;
                this.numeros.push(random);
            },
            sumarNumeros(valor) {
                this.suma += valor;
            }
        },
        components: {
            HijoNumero
        }, 
        data() {
            return {
                numeros: [34,55,66],
                suma: 0
            }
        }
    }
</script>