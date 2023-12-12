<template>
    <div>
        <h1>Watcher</h1>
        <label for="">
            Ingrese equipo de futbol
            <input type="text" v-model="equipo">
        </label>
        <p v-show="estaEscribiendo">Escribiendo...</p>
    </div>
</template>

<script>
export default {
    name: 'WatcherPrueba',

    data() {
        return {
            equipo: '',
            estaEscribiendo:false
        };
    },

    watch: {
        equipo(actual, anterior) {
            console.log(`El equipo cambio. Antes:${anterior} Ahora:${actual}`);
            this.estaEscribiendo=true;
            setTimeout(() => {
                this.estaEscribiendo=false;
            }, 2000);
        }
    }
};
</script>

<style scoped></style>