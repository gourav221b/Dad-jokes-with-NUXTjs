<template>
<div>
  <h2>
    Welcome to arjos paradise
  </h2>
    <nuxt-link to="jokes">Lets see some jokes</nuxt-link>
</div>
</template>

<script>
export default {
head()
{
  return {
    title:"Welcome to arjos paradise",
    meta:[
      {
        hid:'description',
        name:'description',
        content:'best place for arjo'
      }
    ]
  }
},


}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Edu+TAS+Beginner:wght@400;600;700&display=swap');
*
{
  font-family: 'Roboto',sans-serif;
}
a
{
  text-decoration: none;
}
body
{
  max-width: 100vw;
  overflow-x:hidden ;
  padding: 0 2vw;
}
</style>
