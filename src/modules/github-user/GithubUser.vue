<template>
  <div class="card-container">
    <!-- este componente emite un evento para buscar un asuario -->
    <CardSearchUser />
    <!-- 
      mostrar este componente si existe un usuario
      este componente necesita una un objeto {user}
    -->
    <CardUser />
    <!--
      mostrar este componente si no hay un usuario
    - también este componente recibe un mensaje opcional
    -->
    <CardUserDefault />
  </div>
</template>

<script setup>
  import { ref } from 'vue';
  import CardUser from './components/CardUser.vue';
  import CardSearchUser from './components/CardSearchUser.vue';
  import CardUserDefault from './components/CardUserDefault.vue';
  const user = ref(null);
</script>

<style scoped>
  .card-container {
    width: 100%;
    max-width: 30rem;
  }
</style>
