<template>
  <div class="menu-wrapper">
    <div class="main-menu-container">
      <div class="menu-item" v-for="item in menuItems" @click="setSubMenu(item[0])">
        <img :src="item[1]"/>
        <span>{{item[0]}}</span>
      </div>
    </div>

    <SubMenu v-if="this.subMenu.length" :subMenuCat="subMenu"/>
    <ColorMenu v-if="this.subMenu.length" :subMenuCat="subMenu"/>

  </div>
</template>

<script>
import SubMenu from '@/components/SubMenu';
import ColorMenu from '@/components/ColorMenu';

export default {
  name: 'MainMenu',
  components: {
    SubMenu,
    ColorMenu
  },
  data () {
    return {
      iconBody: ['bodies', require('@/assets/bodyparticons/Body2.svg')],
      iconBrow: ['brows', require('@/assets/bodyparticons/brow2.svg')],
      iconEar: ['ears', require('@/assets/bodyparticons/ear2.svg')],
      iconEye: ['eyes', require('@/assets/bodyparticons/eye2.svg')],
      iconHair: ['hair', require('@/assets/bodyparticons/hair1-head2.svg')],
      iconHead: ['skin', require('@/assets/bodyparticons/head2.svg')],
      iconMouth: ['mouths', require('@/assets/bodyparticons/mouth2.svg')],
      iconNose: ['noses', require('@/assets/bodyparticons/nose1.svg')],
      menuItems: [],
      subMenu: ''
    }
  },
  mounted: function() {
    this.menuItems = [this.iconBody, this.iconBrow, this.iconEar, this.iconEye, this.iconHair, this.iconHead, this.iconMouth, this.iconNose]
  },
  methods: {
    setSubMenu: function(cat) {
      this.subMenu = cat;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.menu-wrapper {
  width: 100px;
  background: linear-gradient(left, #FF512F, #F09819);
  position: fixed;
  bottom: 0;
  left: 0;
  top: 0;
}
.main-menu-container {
  display: flex;
  height: 100%;
  margin: 0 auto;
  justify-content: space-between;
  flex-direction: column;
}
.main-menu-container .menu-item:hover {
  background: #FF512F;
  cursor: pointer;
}
.menu-item {
  max-height: 130px;
  width: 100px;
}
.menu-item img {
  max-height: 100px;
  min-width: 100%;
}
.menu-item span {
  color: #fff;
  text-transform: uppercase;
  padding-bottom: 10px;
  font-family: 'Dokdo', cursive;
}

</style>
