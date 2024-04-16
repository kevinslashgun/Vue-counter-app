<template>
  <Header />
  <main>
    <Counter />
  </main>
</template>

<script>
import Header from './components/Header.vue';
import Counter from './components/Counter.vue';

export default {
  components: {
    Header,
    Counter
  }
};
</script>

<style scoped>
main {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem;
}
</style>