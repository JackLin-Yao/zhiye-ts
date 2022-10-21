<template>
  <div class="container">
    <GlobalHeader :user="currentUser"></GlobalHeader>
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import 'bootstrap/dist/css/bootstrap.min.css'
import ColumnList, { ColumnProps } from '@/components/ColumnList.vue';
import GlobalHeader, { UserProps } from '@/components/GlobalHeader.vue';
const testData: ColumnProps[] = [
  {
    id: 1,
    title: '专栏',
    description: '阿三哥卡补充消耗',
    avatar: 'https://avatars.githubusercontent.com/u/67159736?s=40&v=4'
  },
  {
    id: 1,
    title: '专栏',
    description: '阿三哥卡补充消耗',
    avatar: 'https://avatars.githubusercontent.com/u/67159736?s=40&v=4'
  },
  {
    id: 1,
    title: '专栏',
    description: '阿三哥卡补充消耗',
    avatar: 'https://avatars.githubusercontent.com/u/67159736?s=40&v=4'
  },
  {
    id: 1,
    title: '专栏',
    description: '阿三哥卡补充消耗',
    avatar: 'https://avatars.githubusercontent.com/u/67159736?s=40&v=4'
  },
  {
    id: 1,
    title: '专栏',
    description: '阿三哥卡补充消耗',
    // avatar: 'https://avatars.githubusercontent.com/u/67159736?s=40&v=4'
  }
]
const currentUser:UserProps = {
  isLogin:true,
  name:'yhjk'
}
export default defineComponent({
  name: 'App',
  components: {
    ColumnList,GlobalHeader
  },
  setup() {

    return {
      list: testData,
      currentUser
    }
  }
})
</script>

<style lang="scss">

</style>
