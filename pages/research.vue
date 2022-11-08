<template>

</template>
<script>
import Card from '../components/Card.vue'
import axios from 'axios'

export default {
    components: {
        Card
    },
    data() {
        return {
            loading: true,
            countries: null, 
            errored: false
        }
    },
    mounted() {
        axios
            .get('https://portal.ehri-project.eu/api/graphql')
            .then(response => [this.countries = response.data])
            .catch(error => {
                console.log[error]
                this.errored = true
            })
            .finally(() => this.loading = false)
    }
}

</script>
<style>
.container {
    min-height: 100vh;
    max-width: 1200px;
    margin: auto;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    text-align: center;
    flex-wrap: wrap;
}

.heading {
    text-align: center;
    font-size: 2rem;
    color: #555555;
    margin: 2rem auto;
}

img {
    max-width: 150px;
}

.title {
    font-family: "Quicksand", "Source Sans Pro", system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    display: block;
}
</style>