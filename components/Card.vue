<template>
    <article class="card">
        <!-- Incorporate data from an API. With returned data, build corresponding component and use v-for to loop over the data. -->
        <!-- Props validation and 4 data points  -->
        <h2 class="card__title">{{ country.name }}</h2>
        <p class="card__history">{{ country.history }}</p>
        <p class="card__situation">{{ country.situation }}</p>
        <p class="card__summary">{{ country.summary }}</p>
        <a class="card__link" href="https://">{{ country.links}}</a>
        
    </article>
   </template>
   
   <script>
   import links from '../api/index.js'
   export default {
            name: 'ResearchPage',
        data () {
          return {
            
          }
        },
        props: {
            card__title: {type: String},
            card__history: {type: String},
            card__situation: {type: String},
            card__summary: {type: String},
            card__link: {type: String}  
        }
    }
   </script>
   
   
   <style lang="scss"  scoped>
   .card {
       margin: 1rem;
       border: 1px solid #000;
       padding: 1.5rem;
       max-width: 1000px;
       min-height: 500px;
       &__img {
           display: block;
           margin-bottom: 1rem;
       }
       &__title {
           font-size: 1rem;
           margin-bottom: .25rem;
       }
       &__copy {
           font-size: .875rem;
       }
   }
   </style>
   
   