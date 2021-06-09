<template>

  <section class="container">
      <div class="row">
          <div 
          class="col-5 col-md-4 col-lg-3"
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

<style>

</style>