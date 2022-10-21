<template>
 <nav class="navbar navbar-dark bg-primary justify-content-between mb-4">
  <a class="navbar-brand">专栏</a>
  <ul v-if="!user.isLogin" class="list-inline mb-0 mr-2">
    <li class="list-inline-item">
      <a href="#" class="btn btn-outline-light my-2">
        登录
      </a>
    </li>
    <li class="list-inline-item">
      <a href="#" class="btn btn-outline-light my-2">
        注册
      </a>
    </li>
  </ul>
  <ul v-else class="list-inline mb-0">
    <li class="list-inline-item mr-2">
     <dropdown :title="`你好${user.name}`"></dropdown>
    </li>

  </ul>
</nav>
</template>

<script lang="ts">
import Dropdown from './Dropdown.vue';
import { defineComponent, PropType } from 'vue'
export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}
export default defineComponent({
  name: 'GlobalHeader',
  components: {Dropdown},
  props:{
    user:{
      type:Object as PropType<UserProps>,
      required: true
    }
  },
  setup(props) {


    return {

    }
  }
})
</script>

<style scoped>

</style>
