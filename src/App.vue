<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import ItemList from './components/ItemList.vue';
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
      <ItemList />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>