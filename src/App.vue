<!--Estrutura de Script-->
<script setup>
  const nomes = ['Gian', 'Paulo', 'Luiza', 'Mônica'];
</script>

<!--Estrutura da página-->
<template>
 <ul>
  <li v-for="nome in nomes">
    {{ nome }}
  </li>
 </ul>
</template>

<!--Estilo da página-->
<style scoped>

</style>
