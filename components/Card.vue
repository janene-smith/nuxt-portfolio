<template>

</template>
   
   <script>
   export default {
            name: 'ResearchPage',
        data () {
          return {
            
          }
        },
        props: {
            organization: {type: String}, 
            attributes: {type: String},  
            name: {type: String},
            address: {type: String} 
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
   
   