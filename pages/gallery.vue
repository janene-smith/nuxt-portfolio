<template>
    <div id="app">
        <nuxt-link to="/gallery">
            
        </nuxt-link>
        <h1 class="ml-2 mb-1">{{ title }}</h1>
        <!-- <a href="/gallery">...</a> (+Vue Router & prefetching) -->
      <!-- <div>
        <img 
          alt="Panorama Arromanches by Olivier Rault" 
          src="../static/AdobeStock_42498313.jpeg" 
          width=100% 
          height=230px 
        />
      </div> -->
        <div class="image-wrapper">
            <!-- Come back later and work on adding in the figure, image, and fig caption components -->
              <imgComponent 
                v-for="(image, id) in images"
                :key="id" 
                :src="image.src" 
                :alt="image.alt" 
                :title="image.title" 
              />
     
   
        </div>
    </div>
  </template>
  
  <script>
  // eslint-disable-next-line
   /* eslint-disable */
   import imgComponent from '../components/imgComponent.vue'
   export default {
        components: {
          imgComponent
        },
        data () {
          return {
            title: 'Image Gallery',
            images: [
              {
                src: require('../static/G-Croom-WWII-006-th.jpg'), 
                alt: 'United States MPs on motorbikes in France, 1945', 
                title: 'United States MPs on motorbikes in France, 1945'
              },
              {
                src: require('../static/G-Croom-WWII-010-th.jpg'),
                alt: 'Unknown woman and MP Gerald Croom standing with Military Police Jeep',
                title: 'Unknown woman and MP Gerald Croom standing with Military Police Jeep'
              },
              {
                src: require('../static/G-Croom-WWII-011-th.jpg'),
                alt: 'Unknown man and child infront of Hotel Bellevue; Deauville, France, 1945',
                title: 'Unknown man and child infront of Hotel Bellevue; Deauville, France, 1945'
              },
              {
                src: require('../static/G-Croom-MP-bike-WWII.jpg'),
                alt: 'MP soldier Gerald Croom on motorbike',
                title: 'MP soldier Gerald Croom on motorbike'
              },
              {
                src: require('../static/Clarence-Rogers_Andrew-Miller-Texas-th.jpg'),
                alt: 'Clarence Rogers with Andrew Miller of Texas',
                title: 'Clarence Rogers with Andrew Miller of Texas'
              },
              {
                src: require('../static/Croom_Staff-Sgt-th.jpg'),
                alt: 'Gerald Croom with Staff Sgt, unknown.',
                title: 'Gerald Croom with Staff Sgt, unknown.'
              },
            ],
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
    }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style lang="scss" scoped>
  h3 {
    margin: 40px 0 0;
  }
  h2 {
    margin-left: .5rem;
  }
  .image-wrapper {
    margin-left: 2rem;
    margin-right: 2rem;
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
  // Gallery Image Page thumbnail
  .thumbnail {
    float: left;
    width: 478px;
    height: 330px;
    object-fit: cover;
    padding: 15px;
    
  }
  
  
  </style>
  