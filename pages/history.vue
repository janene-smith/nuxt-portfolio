<template>
    <!-- In the future come back and figure our adding links into accordion -->
  <div id="app">
        <nuxt-link to="/history">
            
        </nuxt-link>
        <!-- <a href="/history">...</a> (+Vue Router & prefetching) -->
    <div>
      <h1 class="ml-2 mb-1">{{ title }}</h1>
      <!-- <img class="header" alt="Pointe du Hoc, Cricqueville-en-Bessin, Normandie, Calvados, France By Pascal Moulin " src="../static/AdobeStock_175334157.jpeg" width=100% height=230px />
      <title>Pointe du Hoc, Cricqueville-en-Bessin, Normandie, Calvados, France By Pascal Moulin</title>
            <rect width=100% height=100% ></rect>
            <text class="bg-dark text-white text-right mb-3" x=50% y=50% dy=.10em>Pointe du Hoc, Cricqueville-en-Bessin, Normandie, Calvados, France by Pascal Moulin</text>
      <hr /> -->
    </div>
    <div class="accordion" :id="`accordionExample${id}`" v-for="(account, id) in accounts" :key="id" >
      <div class="card">
          <div class="card-header" id="headingOne">
              <h2 class="mb-0">
                  <button class="btn btn-link text-dark text-decoration-none collapsed" type="button" data-toggle="collapse" data-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
                    {{ account.title }} 
                  </button>
              </h2>
          </div>

          <div id="collapseOne" class="collapse" aria-labelledby="headingOne" :data-parent="'#accordionExample'+id">
              <div class="card-body">
                {{ account.answer }}
              </div>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
import imgComponent from '../components/imgComponent.vue'
export default {
    name: 'HistoryPage',
    props: ['account', 'index', 'open'],
  data() {
    return {
      title: 'World War II History found in the pages of an Album',
      accounts: [
        {
          id: 1,
          title: "World War II Informational Links",
          answer: 'href="http://www.omaha-beach.eu">Omaha Beach Project June 6, 1944',
          open: true
        },
        {
          id: 2,
          title: "WWII Newsprint in color",
          answer: 'Newspaper clipping found in my uncles scrap album of paintings by Ogden Pleissner. Assumed titles: ENGLANDs AIRFIELDS and FLOCKS OF FLYING FORTRESSES. Source unknown.',
          image: '../static/Englands-Airfields-a.jpg',
          open: false
        },
        {
          id: 3,
          title: 'The Stars and Stripes Paris Edition | Monday, May 7, 1945',
          answer: 'Hello',
          image: '../static/front-page.jpg',
          open: false
        }
      ]
    }
  },
  methods: {
    toggleOpen: function (index) {
      this.accounts = this.accounts.map((account, i) => {
        if (index === i) {
          account.open = !account.open;
        } else {
          account.open = false;
        }

        return account;
      });
    }
  },
  head() {
      return {
        title: this.title,
        meta: [
          // hid is used as unique identifier. Do not use `vmid` for it as it will not work
          {
            hid: 'description',
            name: 'description',
            content: 'My custom description'
          }
        ]
      }
    }
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.container-fluid {
  display: grid
}
h1 {
  margin-left: 2rem;
  margin-bottom: 1rem;
  text-align: left;
}
h3 {
  margin: 40px 0 0;
}
img.header {
  margin-bottom:0rem;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}



</style>
