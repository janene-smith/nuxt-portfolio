<template>
    <div>
        <!-- This is where the nav goes -->
        <nav>
            <NuxtLink to="/">Home</NuxtLink> |
            <NuxtLink to="/gallery">Gallery</NuxtLink> |
            <NuxtLink to="/history">History</NuxtLink> |
            <NuxtLink to="/grid">Rememberance</NuxtLink> |
            <NuxtLink to="/research">EHRI</NuxtLink> 
        </nav>
        <Nuxt />
        <!-- This is where you would put the  footer  -->
    </div>
  </template>
  <script>
   
  </script>
  <style>
    html {
        font-family: "Source Sans Pro", Roboto, "Helvetica Neue", Arial, sans-serif;
        font-size: 16px;
        word-spacing: 1px;
        -ms-text-size-adjust: 100%;
        -webkit-text-size-adjust: 100%;
        -moz-osx-font-smoothing: grayscale;
        -webkit-font-smoothing: antialiased;
        box-sizing: border-box;
    }

    *, *:before, *:after {
        box-sizing: border-box;
        margin: 0;
    }

  </style>
