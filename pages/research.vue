<template>
    <div id="app">
        <div class="wrapper">
            <h1 class="heading">EHRI</h1>
            <h2 class="heading">European Holocaust Research Infrastructure</h2>
            <section class="container">
                <h4>Listing of organizations and their location</h4>
                <!-- Create a child component to display the information and pass the data as props --> 
                <ul>
                    <li v-for="(organization, id) in organizations" :key="id">
                        <span v-if="organization.attributes.name">
                            {{ id }}.   {{ organization.attributes.name }} 
                            {{ organization.attributes.address.organization }}
                        </span>
                    </li>
                </ul>
            </section> 
        </div>     
    </div>
</template>

<script>
// Run npm install axios
import axios from 'axios';

// Import child component
import Card from '../components/Card.vue';

export default {
    name: 'researchPage',
    data() {
        return {
          organizations: [],
        };
    },
    components: {
        // Register child component
    },
    mounted() {
        axios
            .get('https://portal.ehri-project.eu/api/v1/search')
            .then(response => [this.organizations = response.data.data])
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
    margin:  auto;
}

h4 {
    text-decoration: underline;
}
li {
    list-style-type: none;
    text-align: left;
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