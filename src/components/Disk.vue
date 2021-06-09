<template>

  <section class="container">
      <div class="row">
          <div 
          class="col-6 col-md-2 col-lg-2"
          v-for="cover in cover" :key="cover.id"
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
import axios from 'axios';

export default {
    name: "Disk",
    components: {
        Covers
    },
    data: function() {
        return {
            cover: []
        }
    },
    created: function() {
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(
                (response) => {
                    this.cover = response.data.response;
                }
            )
            .catch()
    }
}

</script>

<style lang="scss" scoped>

    .row {

        justify-content: center;

        div {
            margin: 0 1%;
            margin-bottom: 10px;
            height: 250px;
        }
    }

</style>