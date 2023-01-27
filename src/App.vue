<template>
  <HeaderComponent></HeaderComponent>
  <TodoContainer></TodoContainer>
</template>

<script>

import HeaderComponent from './components/HeaderComponent.vue';
import TodoContainer from './components/TodoContainer.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    TodoContainer
  }
}
</script>

<style>
@import'~bootstrap/dist/css/bootstrap.css';
@import'~bootstrap-icons/font/bootstrap-icons.css';
</style>
