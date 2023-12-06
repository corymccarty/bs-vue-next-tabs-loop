<script setup lang="ts">
import { ref } from 'vue'

const tabIndex = ref(0)

function linkClass(classTabIndex: number) {
  console.debug(
    `linkClass with classTabIndex of ${classTabIndex} and tabIndex (v-model) of ${tabIndex.value}`
  )
  if (tabIndex.value === classTabIndex) {
    return ['bg-primary', 'text-light']
  } else {
    return ['bg-light', 'text-info']
  }
}
</script>

<template>
  <BTabs v-model="tabIndex">
    <BTab title="Tab 1" :title-link-class="linkClass(0)">
      <p>Tab 1</p>
    </BTab>
    <BTab title="Tab 2" :title-link-class="linkClass(1)">
      <p>Tab 2</p>
    </BTab>
  </BTabs>
</template>
