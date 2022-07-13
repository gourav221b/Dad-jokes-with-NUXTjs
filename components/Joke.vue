<template>
  <nuxt-link :to="'jokes/'+id">
<div class="jokeWrapper">
    <p class="joke">{{joke.substring(0,30)}}...</p>
</div>
  </nuxt-link>
</template>
<script>
export default {
  name:'joke',
  props:['joke','id'],

}
</script>
<style>
.jokeWrapper
{
 width: 25vw;
  height: 100px;
  margin: 5px ;
  border: 1px solid rgba(0, 0, 0, 0.36);
  border-radius: 5px;
  transition: 0.5s ease;
}
.joke
{
  padding: 10px ;
  color: #000;
  text-align: center;
  font-size: 20px;
  font-family: 'Edu TAS Beginner', cursive;
  font-weight: 600;
}
.jokeWrapper:hover
{
  background: #ececec;
}
@media screen and (max-width:600px) {
  .jokeWrapper
  {
    width: 80vw;
  }

}
</style>
