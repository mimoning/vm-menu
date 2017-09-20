<template>
  <div @contextmenu.prevent="showMenu = true">
    <span>aaaa</span>
    <slot></slot>
    <span ref="menu" v-if="showMenu">This is an menu</span>
  </div>
</template>
<script>
  export default {
    data () {
      return {
        showMenu: false
      }
    },
    beforeCreate () {
      document.addEventListener('click', e => {
        const menu = this.$refs.menu
        // 如果在菜单之外点击，把菜单消除
        if (!e.path.includes(menu)) {
          this.showMenu = false
        }
      })
    }
  }
</script>
