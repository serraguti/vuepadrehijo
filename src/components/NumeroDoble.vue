<template>
    <div>
        <h1>Número doble parámetros</h1>
        <h1 style="color:orange" v-if="mensaje">
            {{mensaje}}
        </h1>
        <div v-else>
            <h2 style="color:blue">
                El número recibido es: {{numero}}
            </h2>
            <h2 style="color:red">
                El doble es {{doble}}
            </h2>
        </div>
    </div>
</template>

<script>
    export default {
        name: "NumeroDoble",
        mounted() {
            //DEBEMOS CAPTURAR LOS PARAMETROS EN ESTE METODO
            console.log(this.$route.params.numero);
            if (this.$route.params.numero == ""){
                console.log("Sin parámetros");
                this.mensaje = "No tenemos parámetros";
            }else{
                this.numero = this.$route.params.numero;
                this.doble = parseInt(this.numero) * 2;
            }
        }, data() {
            return {
                mensaje: null,
                numero: 0,
                doble: 0
            }
        }
    }
</script>