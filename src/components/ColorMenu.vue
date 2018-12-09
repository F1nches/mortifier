<template>

    <div class="color-menu-wrapper">
      <div class="color-options-container">
        <div class="color-option" v-for="color in colors" :style="{background: color.base}" :data-color="color.base">
        </div>
      </div>
    </div>

</template>

<script>
export default {
  name: 'ColorMenu',
  data () {
    return {
      colors: [
        {
          base: '#f44336',
          name: 'Reds',
          variants: ['#ffcdd2', '#e57373', '#f44336', '#d32f2f', '#b71c1c']
        },
        {
          base: '#E91E63',
          name: 'Pinks',
          variants: ['#F48FB1', '#EC407A', '#D81B60', '#AD1457', '#880E4F']
        },
        {
          base: '#9C27B0',
          name: 'Purples',
          variants: ['#CE93D8', '#AB47BC', '#8E24AA', '#6A1B9A', '#4A148C']
        },
        {
          base: '#3F51B5',
          name: 'Indigos',
          variants: ['#9FA8DA', '#7986CB', '#3F51B5', '#303F9F', '#1A237E']
        },
        {
          base: '#2196F3',
          name: 'Blues',
          variants: ['#90CAF9', '#42A5F5', '#1E88E5', '#1565C0', '#0D47A1']
        },
        {
          base: '#00BCD4',
          name: 'Cyans',
          variants: ['#80DEEA', '#26C6DA', '#00ACC1', '#00838F', '#006064']
        },
        {
          base: '#009688',
          name: 'Teals',
          variants: ['#80CBC4', '#26A69A', '#00897B', '#00695C', '#004D40']
        },
        {
          base: '#4CAF50',
          name: 'Greens',
          variants: ['#A5D6A7', '#66BB6A', '#43A047', '#2E7D32', '#1B5E20']
        },
      ]
    }
  },
  mounted: function() {

  },
  created: function() {

  },
  watch: {

  },
  methods: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.color-menu-wrapper {
  width: 100px;
  position: fixed;
  bottom: 0;
  left: 0;
  top: 0;
  margin-left: 210px;
}
.color-option:first-of-type {
  margin-top: 5px;
}
.color-option {
  width: 100px;
  height: 100px;
  margin: 10px;
}
</style>
