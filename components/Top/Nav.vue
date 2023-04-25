<template>
    <div class="navigation">
        <NuxtLink class="navigation-item" to="/">Home</NuxtLink>
        <NuxtLink class="navigation-item" to="/about">About</NuxtLink>
        <NuxtLink class="navigation-item" to="/gallery">Gallery</NuxtLink>
        <NuxtLink class="navigation-item" to="/cars/nasa">Nasa</NuxtLink>
        <NuxtLink class="navigation-item" to="/cars/">cars</NuxtLink>

    
      </div>
  </template>
  
  <script>
  export default {
    name: 'TopNav'
  }
  </script>
  <style scoped>
    .navigation {
        display: flex;
        flex-wrap: wrap;
        background-color:  rgb(69, 140, 233);
        min-height: 50px;
        margin-left: 5px;
    }

    .navigation-item {
        padding: 15px 5px 10px 5px;
        text-decoration: none;
        color: white
    }

    .navigation-item:hover {
        color: rgb(183, 187, 223)
    }
  </style>
