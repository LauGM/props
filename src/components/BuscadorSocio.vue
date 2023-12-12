<template>
    <div>
        <label for="numSoc">
            Numero socio
            <input type="number" name="numSoc" v-model="numero">
        </label>
        <button @click="buscarSocio()">🔍</button>
        <p v-if="resultado">Socio nro: {{ resultado.numero }} Nombre: {{ resultado.nombre }}</p>
        <p v-else-if="resultado == undefined">El socio no existe</p>
        <p v-else>Ingrese un numero</p>
    </div>
</template>

<script>
export default {
    name: 'BuscadorSocio',
    props:{
        socios:Array,
    },
    data() {
        return {
            numero:'',
            resultado:''
        };
    },

    methods: {
        buscarSocio(){
            this.resultado = this.socios.find(socio => socio.numero === parseInt(this.numero));
            
            console.log(this.resultado);
            } 
        }
};
</script>