<template>
  <div class="app">
    <Header />
    <Content />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Content from './components/Content.vue'

export default {
  name: 'App',
  components: {
    Header,
    Content
  }
}
</script>

<style>
:root {
  --background: rgb(58, 56, 56);
  --color-grey: rgb(235, 231, 231);
  --border-grey: rgb(63, 60, 60);
  --hover-grey: rgb(218, 213, 213);
  --opasity-grey: rgb(27, 26, 26, 0.7);
}

.app {
  height: 100vh;
  width: 100%;
  background-color: var(--background);
  display: flex;
  flex-direction: column;
}

</style>
