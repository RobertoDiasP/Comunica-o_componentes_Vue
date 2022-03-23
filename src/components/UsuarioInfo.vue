<template>
  <div class="componente">
    <h2>As Informações de Usuário</h2>
    <p>Vários detalhes...</p>
    <p>
      Nome do usuario: <strong>{{ nome }}</strong>
    </p>
    <p>
      Idade é: <strong>{{ idade }}</strong>
    </p>
    <button @click="ReinicicarNome">Reiniciar nome</button>
    <button @click="reiniciarfn">Reiniciar nome callback</button>
  </div>
</template>

<script>
import barramento from "@/barramento";

export default {
  props: {
    nome: { type: String, default: "anonimo" },
    reiniciarfn: Function,
    idade: Number,
  },
  methods: {
    ReinicicarNome() {
      this.nome = "Pedro Silva";
      this.$emit("mudounome", this.nome);
    },
  },
  //created() {
  //barramento.$on("IdadeMudou", (idade) => {});
  //},
};
</script>

<style scoped>
.componente {
  flex: 1;
  background-color: #ec485f;
  color: #fff;
}
</style>
