<template>
  <div @contextmenu.prevent="openMenu">
    <slot></slot>
    <menu-content ref="menu" v-if="isShow"
      @close-menu="isShow = false"
      :position="menuPosition"
    >
      <slot name="menu"></slot>
    </menu-content>
  </div>
</template>
<script>
  import MenuContent from './vm-menu-content'

  export default {
    components: {
      MenuContent
    },
    data () {
      return {
        // 控制菜单是否显示
        isShow: false,
        // 控制菜单的位置
        menuPosition: null
      }
    },
    methods: {
      // 打开菜单
      openMenu (e) {
        this.isShow = true
        // 更新菜单位置
        this.menuPosition = {
          x: e.clientX,
          y: e.clientY
        }
      }
    },
    // 创建时绑定事件，在组件外其他地方右键要把当前组件内的菜单去除
    created () {
      document.addEventListener('contextmenu', e => {
        const trigger = this.$el
        // 如果发生右键事件的事件冒泡序列中没有当前组件的话，则判断在组件外右键
        if (!e.path.includes(trigger)) {
          this.isShow = false
        }
      })
    }
  }
</script>
