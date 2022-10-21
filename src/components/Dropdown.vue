<template>
  <div class="dropdown" ref="dropdownRef">
    <a href="#" class="btn btn-outline-light my-2 dropdown-toggle" @click="toggelOpen">
      {{title}}
    </a>
    <ul class="dropdown-menu" :style="{display:'block'}" v-if="isOpen">
      <li><a class="dropdown-item" href="#">Action</a></li>
      <li><a class="dropdown-item" href="#">Another action</a></li>
      <li><a class="dropdown-item" href="#">Something else here</a></li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, onUnmounted, ref } from 'vue'
import useClickOutside from '@/hook/useClickOutside';

export default defineComponent({
  name: 'Dropdown',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup() {
    const isOpen = ref(false)
    const dropdownRef = ref<null | HTMLElement>(null)
    const toggelOpen = () => {
      isOpen.value = !isOpen.value
    }
    // const handler = (e: MouseEvent) => {
    //   if (dropdownRef.value) {
    //     if (!dropdownRef.value.contains(e.target as HTMLElement) && isOpen.value) {
    //       isOpen.value = false
    //     }
    //   }
    // }
    // onMounted(() => {
    //   document.addEventListener('click', handler)
    // })
    // onUnmounted(() => {
    //   document.removeEventListener('click', handler)
    // })
    const clickOutside = useClickOutside(dropdownRef)
      
    return { toggelOpen, isOpen, dropdownRef }
  }
})
</script>

<style scoped>

</style>
