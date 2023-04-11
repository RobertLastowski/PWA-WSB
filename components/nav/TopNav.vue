<template>
    <div class="nav">
        <NuxtLink class="nav-item" to="/">Home</NuxtLink>
        <NuxtLink class="nav-item" to="/about">About</NuxtLink>
        <NuxtLink class="nav-item" to="/gallery">Gallery</NuxtLink>
    </div>
  </template>
  
  <script>
  export default {
    name: 'NavPage'
  }
  </script>
  <style scoped>
    .nav {
        display: flex;
        flex-wrap: wrap;
        background-color:  rgb(69, 140, 233);
        min-height: 50px;
        margin-left: 5px;
    }

    .nav-item {
        padding: 15px 5px 10px 5px;
        text-decoration: none;
        color: white
    }

    .nav-item:hover {
        color: rgb(183, 187, 223)
    }
  </style>