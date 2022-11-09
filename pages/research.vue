<template>
    <div class="wrapper">
        <h1 class="heading">EHRI</h1>
        <h2 class="heading">European Holocaust Research Infrastructure</h2>
        <section class="container" v-if="countries">
            <Card
                 v-for="country of countries"
                 :key="country.id"
                 :country="country"
            />
        </section>      
    </div>
</template>

<script>
import axios from 'axios'
import Card from '../components/Card.vue'

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
            .get('https://portal.ehri-project.eu/api/v1')
            .then(response => [this.countries = response.data])
            .catch(error => {
                console.log[error]
                this.errored = true
            })
            .finally(() => this.loading = false)
    }
}

</script>
<style lang="scss" scoped>
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

.title {
    font-family: "Quicksand", "Source Sans Pro", system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    display: block;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>