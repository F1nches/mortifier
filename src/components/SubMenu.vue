<template>

    <div class="sub-menu-wrapper">
      <transition name="list">
        <div class="sub-main-menu-container" :key="this.menuItems">
            <div class="sub-menu-item" v-for="item in menuItems">
              <img :src="item"/>
            </div>
        </div>
      </transition>
    </div>

</template>

<script>
export default {
  name: 'SubMenu',
  props: ['subMenuCat'],
  data () {
    return {
      catOptions: [
        {
          name: 'ears',
          items: [require('@/assets/bodyparticons/ear2.svg'), require('@/assets/bodyparticons/ear2.svg'), require('@/assets/bodyparticons/ear2.svg'), require('@/assets/bodyparticons/ear2.svg')]
        },
        {
          name: 'eyes',
          items: [require('@/assets/bodyparticons/eye2.svg'), require('@/assets/bodyparticons/eye2.svg'), require('@/assets/bodyparticons/eye2.svg'), require('@/assets/bodyparticons/eye2.svg')]
        },
        {
          name: 'mouths',
          items: [require('@/assets/bodyparticons/mouth2.svg'), require('@/assets/bodyparticons/mouth2.svg'), require('@/assets/bodyparticons/mouth2.svg'), require('@/assets/bodyparticons/mouth2.svg'), require('@/assets/bodyparticons/mouth2.svg'), require('@/assets/bodyparticons/mouth2.svg')]
        },
        {
          name: 'noses',
          items: [require('@/assets/bodyparticons/nose1.svg'), require('@/assets/bodyparticons/nose1.svg'), require('@/assets/bodyparticons/nose1.svg'), require('@/assets/bodyparticons/nose1.svg'), require('@/assets/bodyparticons/nose1.svg'), require('@/assets/bodyparticons/nose1.svg')]
        },
        {
          name: 'hair',
          items: [require('@/assets/bodyparticons/hair1-head2.svg'), require('@/assets/bodyparticons/hair1-head2.svg'), require('@/assets/bodyparticons/hair1-head2.svg'), require('@/assets/bodyparticons/hair1-head2.svg'), require('@/assets/bodyparticons/hair1-head2.svg'), require('@/assets/bodyparticons/hair1-head2.svg')]
        },
        {
          name: 'brows',
          items: [require('@/assets/bodyparticons/brow2.svg'), require('@/assets/bodyparticons/brow2.svg'), require('@/assets/bodyparticons/brow2.svg')]
        },
        {
          name: 'skin',
          items: [require('@/assets/bodyparticons/head2.svg')]
        }
      ],
      menuItems: [],
      catColor: ''
    }
  },
  mounted: function() {

    // console.log('submenucat', this.subMenuCat);
    // for (var i=0; i<this.icons.length; i++) {
    //   this.menuItems.push(this.icons[i]);
    // };
    //
    // console.log(this.menuItems);
  },
  created: function() {

  },
  watch: {
    subMenuCat: function() {
      this.loadCatItems(this.subMenuCat);
    }
  },
  methods: {
    loadCatItems: function(cat) {

      for (var i=0; i<this.catOptions.length; i++) {
        if (this.catOptions[i].name == cat) {
          // console.log('name', cat);
          this.menuItems = [];
          for (var k=0; k<this.catOptions[i].items.length; k++) {
            this.menuItems.push(this.catOptions[i].items[k]);
          };
        }
      }

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.sub-menu-wrapper {
  width: 100px;
  position: fixed;
  bottom: 0;
  left: 0;
  top: 0;
  margin-left: 100px;
}
.sub-main-menu-container {
  display: flex;
  height: 100%;
  margin: 0 auto;
  flex-direction: column;
}
.sub-main-menu-container .sub-menu-item:hover {
  cursor: pointer;
  background: #eee;
}
.sub-menu-item {
  max-height: 100px;
  width: 100px;
  background: #fff;
  margin: 5px 10px;
}

.sub-menu-item img {
  max-height: 100px;
  min-width: 100%;
}
.sub-menu-item span {
  color: #fff;
  text-transform: uppercase;
  padding-bottom: 10px;
  font-family: 'Dokdo', cursive;
}
.list-enter-active, .list-leave-active {
  transition: all 0.5s;
}
.list-enter, .list-leave-to /* .list-leave-active below version 2.1.8 */ {
  opacity: 0;
  /* transform: translateY(-15px); */
}
</style>
