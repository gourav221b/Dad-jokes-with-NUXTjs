<template>
<div>
<header class="header">
  <h1>All about dad jokes</h1>
  <ul>
    <li>
      <nuxt-link to="/">Home</nuxt-link>
    </li>
    <li>
      <nuxt-link to="/about">About</nuxt-link>
    </li>
    <li>
      <nuxt-link to="/jokes">Jokes</nuxt-link>
    </li>
  </ul>
</header>
</div>
</template>

<script>
export default {
name:'AppHeader'
}
</script>

<style>
.header
{

display: flex;
align-items: center;
justify-content: space-between;
flex-wrap: wrap;
padding: 0 5vw;
box-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;
}
ul
{
  list-style: none;
  display: flex;
  margin: 0;
}
ul li
{
  background: #111;
  padding: 5px 15px;
  margin: 10px;
}
ul li a
{

  color: #fff;
}
</style>
