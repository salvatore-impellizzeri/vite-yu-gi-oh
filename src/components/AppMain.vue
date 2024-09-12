<script>
import { store } from '../store.js';
import axios from 'axios';
import SingleCard from './SingleCard.vue';

export default {
  data() {
    return {
      store,
    }
  },

  components: {
    SingleCard
  }
}
</script>

<template> 
    <div class="my-bg-orange">

        <!-- DROPDOWN -->

        <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                Dropdown button
            </button>
            <ul class="dropdown-menu">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><a class="dropdown-item" href="#">Something else here</a></li>
            </ul>
        </div>

        <!-- CARDS -->

        <div class="my-bg-white">
            <div class="container-xxl bg-white p-4 container-cards row">
                <SingleCard v-for="(v, i) in store.allCards" :cardName="v.name" :cardCategory="v.archetype" :cardImg="v.card_images[0].image_url" class="col-2" />
            </div>    
        </div>

    </div>
</template>

<style scoped>

.my-bg-orange{
    background-color: #D48F38;
    padding: 20px;
}

.my-bg-white{
    background-color: white;
}

.container-cards{
    display: flex;
}

</style>
