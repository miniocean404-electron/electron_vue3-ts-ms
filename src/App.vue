<template>
  <div id="content">
    <Menu></Menu>
    <a-config-provider :locale="zhCN">
      <router-view class="main"></router-view>
    </a-config-provider>
  </div>
</template>

<script setup lang="ts">
import { defineEmits } from 'vue'
import Menu from 'components/Menu.vue'
import zhCN from 'ant-design-vue/es/locale/zh_CN'

const emit = defineEmits(['goBack'])
const goBack = () => {
  console.log('go back')
}
</script>

<style lang="scss">
body,
html,
#app,
#content {
  -webkit-app-region: drag; //告诉electron那些在无边框下可以拖拽
  width: 100%;
  height: 100%;
}
#content {
  display: flex;
  width: 100%;
  .main {
    width: inherit;
    height: 96%;
  }
}
</style>
