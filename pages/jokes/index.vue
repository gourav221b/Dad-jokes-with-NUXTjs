<template>
<div>
  <SearchJoke v-on:search-text="searchText"/>
  <div class="jokeContainer">
  <Joke v-for="joke in jokes" v-bind:key="joke.id" :joke="joke.joke" :id="joke.id"/>
  </div>
</div>
</template>
<script>
import axios from "axios"
import Joke from '../../components/Joke.vue'
import SearchJoke from "../../components/SearchJoke.vue";

export default {
    data() {
        return {
            jokes: [],
            empty:""
        };
    },
    async created() {
        const config = {
            headers: {
                "Accept": "application/json",
            }
        };
        try {
            const res = await axios.get("https://icanhazdadjoke.com/search", config);
              if(res.data.results.length>0)
            {this.jokes = res.data.results; this.empty=""}
        }
        catch (error) {
            console.log(error);
        }
    },
    methods:
    {
      async searchText(text){
        const config = {
            headers: {
                "Accept": "application/json",
            }
        };
        try {
            const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
            if(res.data.results.length>0)
            {this.jokes = res.data.results; this.empty=""}
            else
            this.empty="Not available"
        }
        catch (error) {
            console.log(error);
        }
      }
    },
    head() {
        return {
            title: "Jokes section"
        };
    },
    components: { Joke, SearchJoke }
}
</script>
<style>

.jokeContainer
{
  width:100vw;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-evenly;
}
</style>
