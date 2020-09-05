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
    align-items: center;
    justify-content: flex-start;
    color: #000;
    background-color: #97ce4c;

    width: 35%;
    padding: 20px 0;
    border-radius: 15px;
    img {
      border-radius: 50%;
      max-width: 40%;
    }
  }
}
</style>