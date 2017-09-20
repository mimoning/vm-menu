<template>
  <div class="vm-menu" :style="menuStyle">
    <slot>This is content</slot>
  </div>
</template>
<script>
export default {
  data () {
    return {
      menuStyle: ''
    }
  },
  props: {
    position: {
      type: Object
    }
  },
  methods: {
    // 关闭菜单
    closeMenu (e) {
      const menu = this.$el
      // 如果在菜单之外点击，把菜单消除
      if (!e.path.includes(menu)) {
        this.$emit('close-menu')
      }
    },
    // update position
    updatePosition () {
      const left = this.$el.offsetLeft
      const top = this.$el.offsetTop
      this.menuStyle = `transform: translate(${this.position.x - left + 5}px, ${this.position.y - top + 5}px)`
    }
  },
  created () {
    // 当在菜单外进行一下操作时，会关闭菜单
    document.addEventListener('click', this.closeMenu)
  },
  // 组件挂载时
  mounted () {
    // 更新位置
    this.updatePosition()
  },
  // 组件更新时
  updated () {
    // 更新位置
    this.updatePosition()
  }
}
</script>
<style lang="scss">
.vm-menu {
  display: inline-block;
  border: 1px solid #eee;
  box-shadow: 0px 0px 15px 1px rgba(0,0,0,0.2);
  position: absolute;
  background: #fff;
}
</style>

