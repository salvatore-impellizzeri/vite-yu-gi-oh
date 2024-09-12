<script>
import { store } from '../store.js';

export default {
  data() {
    return {
      store,
    }
  }
}
</script>

<!-- All'interno del template ci va un solo figlio -->
<template> 
  <div class="p-4 ">
    <h1> 
        Yu-Gi-Oh Api
    </h1>
  </div>
</template>

<style scoped>

.bg-white{
  background-color: white;
}

h1{
  color: black;
  font-size: 30px;
}

</style>
