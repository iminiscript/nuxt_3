<template>
    <div>
        <div class="media">
            <img :src="data?.Poster" :alt="data.Title" />
            <h2> {{ data.Title }}</h2>
            <ul>
                <li><span>Actors:</span> <span>{{ data.Actors }}</span></li>
                <li><span>Language:</span> <span>{{ data.Language }}</span></li>
                <li><span>Country:</span> <span>{{ data.Country }}</span></li>
                <li><span>Genre:</span> <span>{{ data.Genre }}</span></li>
                <li><span>Released:</span> <span>{{ data.Released }}</span></li>
                <li v-for="rating in data.Ratings" :key="rating.Value">
                <span>{{ rating.Source }}</span> <span> {{ rating.Value}}</span>
                </li>
            </ul>
            <p>
            {{ data.Plot }}
            </p>
        </div>
    </div>
</template>

<script setup>

const route = useRoute();

//console.log(res);

const { data } =  useFetch(`
                    https://www.omdbapi.com/?apikey=3b06b0f&&i=${route.params.id}`, 
                    {
                        pick:["Poster", "Title","Actors", "Language","Country","Genre","Released","rating"]
                    }
                );

// const { data } = useAsyncData(() => {
//                 return $fetch(`https://www.omdbapi.com/?apikey=3b06b0f&&i=${route.params.id}`
//                 );
//             },
//             {
//                 pick:["Poster", "Title","Actors", "Language","Country","Genre","Released","rating"]
//             }
//             );

 console.log(data)


</script>

<style  scoped>
.media {
    max-width: 600px;
    margin: auto;
}

.media img {
    width: 500px;
    height: auto;
    margin: 40px auto;
}
</style>