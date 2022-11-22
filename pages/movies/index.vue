<script lang="ts" setup>

    const inputVal = ref('');
    const searchResult = ref([]);

    async function searchMovie() {
        if (inputVal.value) {
            const { Search } = await $fetch(` https://www.omdbapi.com/?apikey=3b06b0f&&s=${inputVal.value}`);
            console.log("🚀 ~ Search", Search);
            
            searchResult.value = Search;
        } else {

        }
        
    }
    
</script>

<template>
  <div>
    <h1>Movies Database</h1>
    <Props title="Search with Title of the Movies"/>

    <div class="movieSearch">
        <form @submit.prevent="searchMovie">
            <input type="text" placeholder="Movie....." v-model="inputVal">
            <button   type="submit">Search</button>
    
        </form>
     
            <ul>
                <li v-for="result in searchResult" :key="result.imdbID">
                    <nuxt-link :to="{ name: 'movies-id', params: { id: result.imdbID}}">
                        <span> {{ result.Title }} </span>
                        <img :src="result.Poster" :alt="result.Title" />
                    </nuxt-link>

                </li>
            </ul>
        
    </div>
  </div>
</template>

<style scoped>
ul {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    column-gap: 10px;
    row-gap: 25px;
}

img {
    max-width: 100%;
    height: auto;
}

li {
    display: grid;
    padding: 10px;
    box-sizing: border-box;
    text-align: center;
}

span {
    display: block;
    min-height: 50px;
    text-align: center;
    font-size: 1.2rem;
    letter-spacing: -1px;
    font-weight: 600;
}
form {
    width: 450px;
    margin: 20px auto;
    display: flex;
    justify-content: space-between;
}

input {
    border: 1px solid brown;
    padding: 10px;
    width: 300px;
    
}

button {
    padding: 10px;
    border: 1px solid black;
    background-color: black;
    color: aliceblue;
    width: 110px;
    font-size: 1.2rem;
}
</style>


