<!--JavaScript-->
<script setup>
const props = defineProps(['tarefas']);
</script>

<!--Estrutura HTML-->
<template>
  <div>
    <!-- Verifica se há tarefas na lista -->
    <ul v-if="props.tarefas.length > 0" class="list-group mt-4">
      <li class="list-group-item" v-for="tarefa in props.tarefas" :key="tarefa.titulo">
        <input 
          @change="evento => tarefa.finalizada = evento.target.checked" 
          :checked="tarefa.finalizada" 
          :id="tarefa.titulo" 
          type="checkbox">
        <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
          {{ tarefa.titulo }}
        </label>
      </li>
    </ul>

    <!-- Exibe mensagem caso não existam tarefas -->
    <p v-else class="text-muted mt-4">Não existem tarefas pendentes.</p>
  </div>
</template>

<!--Estilo CSS-->
<style scoped>
  .done {
    text-decoration: line-through;
  }
</style>
