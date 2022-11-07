<template>
    <div>
        <h1 style="color:blue">
            {{ nombredeporte }}
        </h1>
        <button @click="seleccionarFavorito">
            Seleccionar favorito
        </button>
    </div>
</template>

<script>
    export default {
        name: "HijoDeporte",
        props: [ "nombredeporte" ],
        methods: {
            seleccionarFavorito() {
                //CUANDO PULSEMOS EN EL HIJO, LLAMAMOS AL METODO
                //DEL PARENT QUE NOS HAN ENVIADO POR props
                this.$emit("seleccionarFavoritoParent", "Su favorito es "
                + this.nombredeporte);
            }
        },
        mounted() {
            //console.log(this.nombredeporte);
        }
    }
</script>