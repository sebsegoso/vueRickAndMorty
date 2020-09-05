<template>
  <div>
    <h1>Componente padre</h1>
    <Personaje v-for="(personaje, i) in personajes" :key="i" :fotoPersonaje="personaje.img" :nombrePersonaje="personaje.nombre" />
    <!-- Mensaje error -->
    <p
      v-if="error"
    >Lo sentimos, no hemos podido acceder a los datos solicitados en este momento, intente nuevamente.</p>
    
  </div>
</template>

<script>
import Personaje from "./components/Personaje";
import axios from "axios";
export default {
  name: "RickAndMorty",
  components: {
    Personaje,
  },
  data() {
    return {
      personajes: [],
      error: false
    };
  },
  mounted() {
    axios
      .get(`https://rickandmortyapi.com/api/character/?page=1`)
      .then((res) => {
        let data = res.data.results;
        console.log(data);
        data.forEach((personaje) => {
          let nombre = personaje.name;
          let img = personaje.image;

          this.personajes.push({ nombre, img });
        });
      })
      .catch((error) => {
        console.log(error);
        this.error = true;
      });
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  box-sizing: content-box;
}

body {
  min-height: 100vh;
  background-color: #000;
  background-image: url(https://rickandmortypod.com/wp-content/uploads/2018/11/cropped-RM_page-header_background1-3.png);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  color: #97ce4c;
}
</style>