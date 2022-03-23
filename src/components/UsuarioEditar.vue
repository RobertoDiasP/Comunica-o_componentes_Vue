<template>
  <div class="componente">
    <h2>Alterar os Dados de Usuário</h2>
    <p>Edite as informações</p>
    <p>
      Nome de usuario: <strong>{{ nome }}</strong>
    </p>
    <p>
      Idade é: <strong>{{ idade }}</strong>
    </p>
    <button @click="AlterarIdadeB">Alterar Idade callback</button>
    <button @click="FunIdade">Alterar idade</button>
  </div>
</template>

<script>
import barramento from "@/barramento";

export default {
  props: {
    nome: String,
    idade: Number,
    AlterarIdadeB: Function,
  },
  methods: {
    FunIdade() {
      this.idade = 33;
      this.$emit("IdadeMudou", this.idade);
    },
  },
};
</script>

<style scoped>
.componente {
  flex: 1;
  background-color: #98b99a;
  color: #fff;
}
</style>
