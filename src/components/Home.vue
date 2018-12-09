<template>
  <div class="app-wrapper">
    <CharacterSet/>
    <MainMenu/>
  </div>
</template>

<script>
import CharacterSet from '@/components/CharacterSet';
import Canvas from '@/components/Canvas';
import MainMenu from '@/components/MainMenu';

export default {
  name: 'Home',
  components: {
    CharacterSet,
    Canvas,
    MainMenu
  },
  data () {
    return {

    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.app-wrapper {
  height: 100%;
}
</style>
