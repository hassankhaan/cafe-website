<template>
  <main>
    <div
      class="flex flex-col items-center justify-center h-screen bg-cover bg-center"
      style="
        background-image: url('https://pronova.se/wp-content/uploads/sites/4/2021/03/IMG_8283-2.jpg');
      "
    >
      <h1 class="text-5xl font-bold mb-6 text-white">
        <span class="text-stroke">Welcome to Our Restaurant</span>
      </h1>
      <router-link to="/menu"
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
      >
        View Menu
      </router-link>
    </div>
  </main>
</template>
<style scoped>

.text-stroke {
  text-shadow: 
    -2px -2px 0 rgb(255, 145, 0),  
    2px -2px 0 rgb(255, 145, 0),
    -2px 2px 0 rgb(255, 145, 0),
    2px 2px 0 rgb(255, 145, 0);
}
</style>
