<template lang="html">
  <div >
   <h3>Episode detail:</h3>
    <p>Title: {{episode.title}}</p>
    <p>Season: {{episode.season}}</p>
    <p>Release date: {{episode.air_date}}</p>
    <characters-list   :episode="episode"></characters-list>
  </div>
</template>

<script>

import CharactersList from './CharactersList.vue'


export default {
  name: 'episode-detail',
  props: ['episode'],
  components: {
    'characters-list': CharactersList
  }
}
</script>

<style lang="css" scoped>
</style>
