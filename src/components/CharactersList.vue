<template lang="html">
  <div >

  <label for="characters-list">Characters List</label>
  <p> {{episode.characters}}</p>
  </div>
</template>

<script>
export default {
  name: 'characters-list',
  props: ['episode'],
  computed:{
    newCharactersArray: function() {
      return this.episode.map((character) => {
        return character.characters;
      })
    }
  }


}
</script>

<style lang="css" scoped>
</style>
