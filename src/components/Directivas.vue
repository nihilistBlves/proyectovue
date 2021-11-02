<template>
    <div>
        <h1>Directivas VUE</h1>
        <hr/>
        <ul v-if="peliculas.length > 0">
            <li v-for="pelicula in peliculas" :key="pelicula">
                {{pelicula}}
            </li>
        </ul>
        <hr/>
        <label>Introduzca un numero:</label>
        <input type="text" v-model="numero"/>
        <h3 v-if="numero >= 0" style="color: green">Positivo</h3>
        <h3 v-else-if="numero < 0" style="color: red">Negativo</h3>
        <hr/>
        <br/>
        <label>Nombre:</label>
        <input type="text" v-model="nombre"/>
        <br/>
        <label>Edad:</label>
        <input type="text" v-model="edad"/>
        <h1>{{nombre}}, {{edad}}</h1>
        <h1>
            {{$data}}
        </h1>
    </div>
</template>

<script>
export default {
    name: "Directivas",
    data() {
        return {
            nombre: "",
            edad: 0,
            numero: 0,
            peliculas: ["Up", "Coco", "Wall-E", "Inside Out"],
        }
    }
}
</script>

<style>

</style>