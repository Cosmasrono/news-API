<script setup>
</script>

<template>
  <main class=" bg-slate-700">
    <div class=" bg-slate-800">
      <nav class=" text-white gap-4 flex flex-row items-center justify-center ">
        <RouterLink to="/" class="">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
 </div>

  <RouterView />
</main>
</template>

<style scoped>
 
</style>
