<template lang="html">
  <div>
    <ul>
      <list-item v-for="(episode, index) in episodes" :key="index" :episode="episode"></list-item>
      
    </ul>
  </div>
</template>

<script>

import ListItem from "./ListItem.vue";


export default {
  name: 'episode-list',
  props: ['episodes'],
  components: {
    'list-item': ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
