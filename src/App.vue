<template>
  <div id="app">

    <Header />

    <main>
      <Disk />
    </main>
    
  </div>
</template>

<script>

import Header from '../src/components/Header';
import Disk from '../src/components/Disk';

export default {
  name: 'App',
  components: {
    Header,
    Disk
  }
}
</script>

<style lang="scss">

@import '~bootstrap/scss/bootstrap';

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

main {
  background-color: #1e2d3b;
  min-height: calc(100vh - 45px);
  padding-top: 50px;
  padding-bottom: 25px;
}

</style>
