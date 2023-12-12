<template>
    <div>
        <h1>Oraculo</h1>
        <label for="">
            Ingrese su pregunta
            <input type="text" v-model="pregunta">
        </label>
        <p v-show="estaEscribiendo">Pensando...</p>
        <p>{{ respuesta }}</p>
        <img :src="imagen" alt="">
    </div>
</template>

<script>
export default {
    name: 'OraculoWatcher',

    data() {
        return {
            pregunta:'',
            respuesta:'',
            imagen:'',
            estaEscribiendo:false,
        };
    },

    watch: {
        pregunta() {
           if(this.pregunta.includes('?')){
            this.estaEscribiendo=true;
            setTimeout(() => {
                this.estaEscribiendo=false;
            }, 2000);

            fetch('https://yesno.wtf/api')
                .then(resp => resp.json())
                .then(data => {
                    console.log(data);
                    this.respuesta=data.answer;
                    this.imagen=data.image;
                })
           } 
        }
    }
};
</script>

<style scoped></style>