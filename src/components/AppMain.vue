<script>
import { store } from '../store.js';

export default {
  data() {
    return {
      store,
    }
  },
}
</script>

<template> 
  <div>
    <header>
        <h1> 
            {{ message }}
        </h1>
    </header>
  </div>
</template>

<style scoped>

</style>
