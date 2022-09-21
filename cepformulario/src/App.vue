<script>
import axios from "axios";
export default {
  data() {
    return {
      cep: "",
      endereco: {},
    };
  },
  methods: {
    async buscar() {
      const url = `https:/viacep.com.br/ws/${this.cep}/json`;
      const res = await axios.get(url);
      this.endereco = res.data;
    },
  },
};
</script>

<template>
  <div class="container">
    <h1>Busca CEP</h1>
    <form @submit.prevent="buscar">
      <input type="text" v-model="cep" placeholder="CEP" />
      <button type="submit">Buscar</button>
    </form>
    <form class="end">
      <label for="rua">Rua</label>
      <input type="text" v-model="endereco.logradouro" />
      <label for="rua">Bairro</label>
      <input type="text" v-model="endereco.bairro" />
      <label for="rua">DDD</label>
      <input type="text" v-model="endereco.ddd" />
      <label for="rua">Cidade</label>
      <input type="text" v-model="endereco.localidade" />
      <label for="rua">UF</label>
      <input type="text" v-model="endereco.uf" />
      <label for="rua">IBGE</label>
      <input type="text" v-model="endereco.ibge" />
    </form>
  </div>
</template>

<style>
.container {
  background-color: #fcb772;
  padding: 10px;
}
.end {
  display: flex;
  flex-direction: column;
}
</style>
