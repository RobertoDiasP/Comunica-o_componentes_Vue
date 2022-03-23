<template>
  <div class="componente">
    <h2>As Informações de Usuário</h2>
    <p>Vários detalhes...</p>
    <p>
      Nome do usuario: <strong>{{ nome }}</strong>
    </p>
    <button @click="ReinicicarNome">Reiniciar nome</button>
    <button @click="reiniciarfn">Reiniciar nome callback</button>
  </div>
</template>

<script>
export default {
  props: {
    nome: { type: String, default: "anonimo" },
    reiniciarfn: Function,
  },
  methods: {
    ReinicicarNome() {
      this.nome = "Pedro Silva";
      this.$emit("mudounome", this.nome);
    },
  },
};
</script>

<style scoped>
.componente {
  flex: 1;
  background-color: #ec485f;
  color: #fff;
}
</style>
