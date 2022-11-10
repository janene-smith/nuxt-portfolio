<template>
    <article class="card">
        <!-- Incorporate data from an API. With returned data, build corresponding component and use v-for to loop over the data. -->
        <!-- Props validation and 4 data points  -->
        <h2 class="card__title">{{ country.name }}</h2> <!-- Data search attribute "name": "<Country>" -->
        <p class="card__history">{{ country.history }}</p>  <!-- Data search attribute "history": "<String>" -->
        <p class="card__situation">{{ country.situation }}</p> <!-- Data search attribute "situation": "<String>" -->
        <p class="card__summary">{{ country.summary }}</p> <!-- Data search attribute "summary": "<String>" -->
        <a class="card__link" href="https://">{{ country.links}}</a> <!-- Data search "links" "self" or "search": "https://portal.ehri-project.eu/api/v1/XX" or "https://portal.ehri-project.eu/api/v1/XX/search" where XX is country code -->
        
    </article>
   </template>
   
   <script>
  
   export default {
            name: 'ResearchPage',
        data () {
          return {
            
          }
        },
        props: {
            query: {type: String},  // "Query"
            type: {type: String},   // "Country"
            facet: {type: String}, // "country"
            card__title: {type: String}, // Data Search results: ""
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
   
   