<template>
    <div>
        <h1>Número doble parámetros</h1>
        <button @click="redirectToHome()">
            Go to Home
        </button>
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
        methods:  {
            redirectToHome() {
                this.$router.push("/");
            }, mostrarDoble() {
                this.numero = this.$route.params.numero;
                this.doble = parseInt(this.numero) * 2;
            }
        },
        watch: {
            //EL CONTROL DE LA VARIABLE SE REALIZA 
            //MEDIANTE STRING Y NO SE UTILIZA LA PALABRA this
            '$route.params.numero'(nextVal, oldVal){
                //SI HA CAMBIADO, REALIZAMOS ACCIONES
                if (nextVal != oldVal){
                    //ACCIONES
                    this.mostrarDoble();
                }
            }
        },
        mounted() {
            //DEBEMOS CAPTURAR LOS PARAMETROS EN ESTE METODO
            console.log(this.$route.params.numero);
            if (this.$route.params.numero == ""){
                console.log("Sin parámetros");
                this.mensaje = "No tenemos parámetros";
            }else{
                this.mostrarDoble();
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