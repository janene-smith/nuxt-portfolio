<template>
    <ul>
        <li>
            :identifier="identifier"
            :title="title"
            :place="place"
            :creator="creator"
        </li>
    </ul>
</template>
   
   <script>
   import axios from 'axios';

   export default {
            name: 'ResearchPage',
        data () {
          return {
            
          }
        },
        props: {
            identifier: {type: String}, 
            title: {type: String},  
            place: {type: String},
            creator: {type: String} 
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
   
   