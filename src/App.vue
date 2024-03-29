<template>
  <page />
</template>

<script>
import Page from '@/components/Page.vue';

export default {
  name: 'App',
  components: { Page },
}
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Open Sans', sans-serif;
  font-size: 24px;
}

button {
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
}

.v-enter-active {
  transition: opacity 0.5s linear;
}

.v-enter-from{
  opacity: 0;
}
</style>
