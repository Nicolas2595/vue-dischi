<template>
  <div>
      <label>GENERI</label>
        <select 
           title="Scegli una opzione"
           v-model="searchGender"
           @change="$emit ('selectedGender', searchGender)"
           >
              <option value="All">All</option>

              <!-- STATICO -->
              <!-- <option value="Rock">Rock</option>
              <option value="Pop">Pop</option>
              <option value="Jazz">Jazz</option>
              <option value="Metal">Metal</option> -->

              <!-- DINAMICO -->
              <option 
              v-for="(genre,index) in genres"
              :key="index"
              :value="genre"
              >
                {{ genre }}
              </option>
        </select>
    </div>
</template>

<script>
export default {
    name: "Search",
    data: function() {
        return {
            searchGender: '',
        }
        
    },
    props: ["genres"]
}
</script>

<style lang="scss" scoped>

label {
    margin: 20px;
    color: #2abe59;
}

select {
    width: 100px;
    border-radius: 10px;
    cursor: grab;
    background-color: #2abe59;
}

</style>