<script>
import axios from "axios";
export default {
  data() {
    return {
      cep: "",
    };
  },
  methods: {
    async buscar() {
      const url = `https://www.cepaberto.com/api/v3/cep?cep=01001000`;
      this.resultado = axios.get(url, {
        headers: {
          Authorization: "Token token=3f6dd21bfd46e236e2ba50b948aedf94",
        },
      });
    },
  },
};
</script>
<template>
  <div class="container">
    <h1>Busca CEP</h1>
    <form @submit.prevent="search">
      <input type="text" placeholder="CEP" v-model="cep" />
      <button type="submit">Buscar</button>
    </form>
  </div>
</template>
<style>
.container {
  background-color: #fcb772;
  padding: 10px;
}
</style>
