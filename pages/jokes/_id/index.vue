<template>
  <div>
    <nuxt-link to="/jokes"> &larr;Back to all</nuxt-link>
    <!-- <img :src="jokeImg" alt=""> -->
    <div v-if="joke.id=='0DtrrOZDlyd'">
     <iframe width="956" height="538" src="https://www.youtube.com/embed/xvFZjo5PgG0" title="Rick Roll (Different link + no ads)" frameborder="0" allow='autoplay'></iframe>
    </div>
      <h2>{{joke.joke}}</h2>
      <hr/>
      <small>Joke ID: {{joke.id}}</small>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data(){
    return{
      joke:{},
      jokeImg:{}
    }
  },
   async created() {
        const config = {
            headers: {
                "Accept": "application/json",
            }
        };
        try {
            const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);

            this.joke = res.data;
            this.jokeImg= `https://icanhazdadjoke.com/j/${this.$route.params.id}.png`
            console.log(res)
        }
        catch (error) {
            console.log(error);
        }
    },
    head()
    {
      return{
        title:'Joke'
      }
    }

}
</script>

<style></style>
