<template>
  <div>
        <h1>Juegos conmutados</h1>
        <ul>
          <li v-for="juego in juegos" :key="juego">
            {{ juego | mayusculas }}
            <br/>
            {{ juego | mayusculasParametro("Juegazo") }}
          </li>
        </ul>
        <hr/>
        <ul>
          <li v-for="juego in juegosRojos" :key="juego" v-html="juego">
            {{juego}}
          </li>
        </ul>
  </div>
</template>

<script>
export default {
    name: "JuegosConmutados",
    filters: {
      mayusculas(dato) {
        return dato.toUpperCase();
      },
      mayusculasParametro(dato, descripcion) {
        return dato.toUpperCase() + descripcion;
      }
    },
    computed: {
      //UNA PROPIEDAD CONMUTADA SIEMPRE DEVUELVE VALORES Y NO TIENE PARAMETROS
      juegosRojos() {
        var datos = this.juegos;
        for (var i = 0; i < datos.length; i++) {
          var juego = "<span style='color:red'>" + datos[i] + "</span>";
          datos[i] = juego;
        }
        return datos;
      }
    },
    data() {
      return {
        juegos: ["Parchis", "Oca", "Ajedrez", "Cinquillo"]
      }
    }
}
</script>

<style>

</style>