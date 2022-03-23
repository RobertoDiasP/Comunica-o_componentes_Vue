<template>
  <div class="container">
    <h1>Componente Usuário</h1>
    <p>Esse é um componente muito legal!</p>
    <p>nome é pedro : {{ nome }}</p>
    <button @click="AlterarNome">Alterar Nome</button>
    <hr />

    <div class="componentes">
      <app-usuario-info
        :nome="nome"
        @mudounome="nome = $event"
        :reiniciarfn="reiniciarnome"
      />
      <app-usuario-editar :nome="nome" />
    </div>
  </div>
</template>

<script>
import AppUsuarioInfo from "./UsuarioInfo";
import AppUsuarioEditar from "./UsuarioEditar";

export default {
  components: { AppUsuarioInfo, AppUsuarioEditar },
  data() {
    return {
      nome: "pedro silva",
    };
  },
  methods: {
    AlterarNome() {
      this.nome = "Ana";
    },
    reiniciarnome() {
      this.nome = "Pedro";
    },
  },
};
</script>

<style scoped>
.container {
  background-color: #27363b;
  color: #fff;
  padding: 10px;
}

.container hr {
  margin: 20px 10px;
}

.componentes {
  display: flex;
}

.componentes > * {
  margin: 10px;
}
</style>
