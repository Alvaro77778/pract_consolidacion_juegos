<template>
  <div class="homePadre">
    <Juegos/>
  </div>
</template>

<script>
// @ is an alias to /src
import Juegos from '@/components/Juegos.vue';

export default {
  name: 'HomePadre',
  components: {
    Juegos
  }
}
</script>
