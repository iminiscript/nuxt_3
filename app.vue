<template>
  <div>
    <nav>
      <nuxt-link to="/">Home</nuxt-link>
      <nuxt-link to="/movies">Movies</nuxt-link>
      <nuxt-link target="_blank" to="https://www.youtube.com/">YouTube</nuxt-link>
    </nav>
    <NuxtPage />
  </div>
</template>



<style>
* {
  font-family: 'Courier New', Courier, monospace;
}
h1 {
    text-align: center;
    font-size: 3rem;
    
}

nav {
  display: flex;
  justify-content: space-around;
}

a {
  font-size: 2rem;
  font-weight: 400;
  color: brown;
  text-decoration: none;
  
}

.router-link-active {
  font-weight: 800;
  text-decoration: underline;
  color: rgb(222, 57, 57);
}

</style>