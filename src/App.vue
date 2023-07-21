<script setup>
</script>

<template>

  <header>
    <router-link :to="{name: 'home'}">
      <h1>Movies <span>App</span> </h1>
    </router-link>
  </header>

  <main>
    <div class="container">
      <router-view></router-view>
    </div>
  </main>

</template>

