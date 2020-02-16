<template>
  <div id="app">
    <h1>{{ titulo }}</h1>
    <h2 v-text="subtitulo"></h2>
    <div v-if="tarefas.length <= 0">
      <h3>Nenhuma tarefa cadastrada</h3>
    </div>
    <div v-if="tarefas.length > 0">
      <h3>{{ tarefas.length }} tarefas cadastradas</h3>
      <ul v-for="tarefa in tarefas" v-bind:key="tarefa">
        <li>{{ tarefa }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      titulo: 'Primeiros exemplos',
      subtitulo: 'Subtitulo super legal',
      tarefas: []
    };
  },
  mounted() {
    setTimeout(() => {
      this.tarefas = ['Limpar a casa', 'Estudar Alemão', 'Assistir Parasita'];
    }, 3000);
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
