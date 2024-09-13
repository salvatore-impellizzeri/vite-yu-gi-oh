<script>
import { store } from '../store';
import axios from 'axios';
import SingleCard from './SingleCard.vue';

export default {
  data() {
    return {
      store,
      selectedType: '',
    }
  },

  components: {
    SingleCard
  },

  methods: {
    performSearch() {
      this.$emit('performSearch', this.selectedType);
    }
  },

  created() {
    axios
    .get('https://db.ygoprodeck.com/api/v7/archetypes.php')
    .then((type) => {
      console.log(type.data);
      this.store.searchType = type.data;
      console.log(this.store.searchType);
    })
    .catch((err) => {
        this.store.searchType = [];
    });
  },
}
</script>

<template> 
    <div class="my-bg-orange">

        <!-- DROPDOWN -->

        <form @submit.prevent="performSearch()" class="w-25 mt-4">
            <select @change="performSearch" v-model="selectedType" class="form-control w-25 mb-4">
              <option value="">Select Archetype</option>
              <option v-for="(type, i) in store.searchType" :value="type.archetype_name" :key="i">{{ store.searchType[i].archetype_name }}</option>
            </select>
        </form>

        <!-- INFO N CARDS -->

        <div class="bg-dark p-4">
            <span class="text-white fs-3">Found {{ store.allCards.length }} cards</span>
        </div>

        <!-- CARDS -->

        <div class="my-bg-white">
            <div class="container-cards p-4 container-cards row">
                <SingleCard v-for="(v, i) in store.allCards" :cardName="v.name" :cardCategory="v.archetype" :cardImg="v.card_images[0].image_url" class="col-2" />
            </div>    
        </div>

    </div>
</template>

<style scoped>

.dropdown{
    margin-bottom: 50px;
}

.my-bg-orange{
    background-color: #D48F38;
    padding: 50px 70px;
}

.my-bg-white{
    background-color: white;
}

.container-cards{
    display: flex;
}

</style>
