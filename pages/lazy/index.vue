<template>
  <div class="example">
    <app-type> Basic Usage </app-type>
    <var-space direction="column">
      <img class="cat" v-lazy="lazy" />
      <img class="cat" v-lazy="lazy" />
      <img class="cat" v-lazy="lazy" />
      <img class="cat" v-lazy="lazy" />
      <img class="cat" v-lazy="lazy" />
      <img class="cat" v-lazy="lazy" />
    </var-space>

    <app-type> Background Image Lazy Load </app-type>
    <div class="cat height" v-lazy:background-image="lazy"></div>
  </div>
</template>

<script lang="ts">
import { defineNuxtComponent } from '#app'
import AppType from '~/components/appType.vue'
import { reactive, toRefs } from 'vue'
export default defineNuxtComponent({
  components: {
    AppType,
  },
  setup() {
    const data = reactive({
      lazy: 'https://varlet.gitee.io/varlet-ui/cat.jpg',
    })
    return { ...toRefs(data) }
  },
})
</script>
<style lang="less" scoped>
.cat {
  width: 100%;
  object-fit: cover;
  background-size: cover;
  pointer-events: none;
}
.height {
  height: 200px;
}
.maxHeight {
  max-height: 200px;
}
</style>
