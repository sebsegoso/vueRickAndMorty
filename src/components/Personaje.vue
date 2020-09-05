<template>
  <div>
    <div class="card">
      <img :src="fotoPersonaje" alt="foto personaje" />
      <h3>{{nombrePersonaje}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Personaje",
  props: {
    fotoPersonaje: String,
    nombrePersonaje: String,
  },
};
</script>

<style lang="scss" scoped>
body {
  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    color: #000;
    background-color: #97ce4c;
    opacity: .95;
    padding: 20px 0;
    border-radius: 15px;
    margin: 5px;
    transition: all .5s;
    &:hover{
        opacity: 1;
        box-shadow: 0 0 30px #FFF;
    }
    img {
      border-radius: 50%;
      max-width: 40%;
    }
  }
}
</style>