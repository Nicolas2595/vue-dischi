<template>

  <section class="container">
      <div class="row">

          <div class="search">
              <Search 
              @selectedGender="searchGenders" 
              :genres="genres"
              />
          </div>

          <div 
          class="col-6 col-md-2 col-lg-2 squares"
          v-for="cover in filterGender" :key="cover.id"
          >
            <Covers 
                :item="cover"
            />
          </div>
      </div>
  </section>

</template>

<script>

import Covers from './Covers';
import Search from './Search';
import axios from 'axios';

export default {
    name: "Disk",
    components: {
        Covers,
        Search
    },
    data: function() {
        return {
            cover: [],
            empty: [],
            genres: []
            
        }
    },
     created: function() {
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(
                (response) => {
                    this.cover = response.data.response;

                    this.cover.forEach(
                        (element) => {
                        // console.log(element);
                        if(!this.genres.includes(element.genre)) {
                            this.genres.push(element.genre)
                        }
                        
                    });
                }
            )
            .catch()
    },
    methods: {
        searchGenders: function(text) {
            this.empty = text;
        }
    },
    computed: {
        filterGender: function() {

            if(this.empty == "All") {
                return this.cover
            }

            const newArray = this.cover.filter(element => {
                return element.genre.includes(this.empty)
            })
            return newArray
        }
    }    
   
}
</script>

<style lang="scss" scoped>

    .row {

        justify-content: center;

        .squares {
            margin: 0 1%;
            margin-bottom: 10px;
            height: 250px;
        }
    }

    .search {
        margin-bottom: 30px;
        text-align: center;
    }

</style>