<template>
  <div class="menu-wrapper">
    <div class="main-menu-container">
      <div class="menu-item" v-for="item in menuItems">
        <img :src="item[1]"/>
        <span>{{item[0]}}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainMenu',
  data () {
    return {
      iconBody: ['bodies', require('@/assets/bodyparticons/Body2.svg')],
      iconBrow: ['brows', require('@/assets/bodyparticons/brow2.svg')],
      iconEar: ['ears', require('@/assets/bodyparticons/ear2.svg')],
      iconEye: ['eyes', require('@/assets/bodyparticons/eye2.svg')],
      iconHair: ['hair', require('@/assets/bodyparticons/hair1-head2.svg')],
      iconHead: ['heads', require('@/assets/bodyparticons/head2.svg')],
      iconMouth: ['mouths', require('@/assets/bodyparticons/mouth2.svg')],
      iconNose: ['noses', require('@/assets/bodyparticons/nose1.svg')],
      menuItems: []
    }
  },
  mounted: function() {
    this.menuItems = [this.iconBody, this.iconBrow, this.iconEar, this.iconEye, this.iconHair, this.iconHead, this.iconMouth, this.iconNose]
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.menu-wrapper {
  width: 100%;
  background: linear-gradient(left, #FF512F, #F09819);
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
}
.main-menu-container {
  display: flex;
  width: 100%;
  max-width: 1000px;
  margin: 0 auto;
  justify-content: space-between;
}
.main-menu-container .menu-item:hover {
  background: #FF512F;
  cursor: pointer;
}
.menu-item {
  height: 130px;
  width: 130px;
}
.menu-item img {
  max-height: 100px;
  min-width: 100px;
}
.menu-item span {
  color: #fff;
  text-transform: uppercase;
  padding-bottom: 10px;
  font-family: 'Dokdo', cursive;
}
</style>
