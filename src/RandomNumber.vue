<template>
  <div>
    <h2>Conditional</h2>

    <h4>{{ bilangan }}</h4>

    <h6 v-if="ganjil">Ganjil</h6>
    <h6 v-if="genap">Genap</h6>

    <button v-on:click="randomNumber">Generate</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      bilangan: 1,
      ganjil: false,
      genap: false,
    };
  },
  
  mounted(){
      this.randomNumber();
  },
  methods: {
    randomNumber() {
      this.bilangan = Math.floor(Math.random() * 10);
      this.showHide();
    },
    showHide() {
      if (this.bilangan % 2 == 0) {
        this.genap = true;
        this.ganjil = false;
      } else {
        this.genap = false;
        this.ganjil = true;
      }
    },
  },
};
</script>

<style scoped></style>
