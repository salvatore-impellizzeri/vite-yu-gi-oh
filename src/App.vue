<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store.js';

export default {
  data() {
    return {
      store,
      allCards: []
    }
  },

  created(){
    this.getDataFromApi();
  },

  methods: {
    getDataFromApi() {
      axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then((res) => {
        console.log(res.data);
        this.store.allCards = res.data.data;
      })
      .catch((err) => {
          this.store.allCards = [];
      })
    }
  },
  
  components: {
    AppHeader,
    AppMain,
  },
}
</script>

<template> 
  <div> 
    <AppHeader />
  </div>
  <div>
    <AppMain @performSearch="getDataFromApi()" /> 
  </div>
</template>

<style lang="scss">
@use 'assets/scss/main.scss' as *;
@import "bootstrap/scss/bootstrap";

header {
    background-color: aquamarine;
    text-align: center;
}

h1 {
    color: lightcoral;
}
</style>

