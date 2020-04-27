<template>
  <div id="app">
    <h1>Breaking Bad</h1>
    <h2>Choose you episode for details</h2>
    <div class="main-container">
      <episode-list :episodes="episodes"></episode-list>
      <episode-detail v-if="selectedEpisode" :characters="characters" :episode="selectedEpisode"></episode-detail>
    </div>
  </div>
</template>

<script>

import CharactersList from '@/components/CharactersList.vue';
import AppHeader from '@/components/AppHeader.vue';
import EpisodeDetail from '@/components/EpisodeDetail.vue';
import EpisodeList from '@/components/EpisodeList.vue';
import {eventBus} from '@/main.js';

export default {
  name: 'App',
  data() {
    return{
      episodes: [],
      characters: [],
      selectedEpisode: null,
      selectedCharacter: null

    }
  },
  mounted(){
    this.fetchEpisodes()
    this.fetchCharacters()


    eventBus.$on('episode-selected', (episode) => {
      this.selectedEpisode = episode;
    })
  },
  methods: {
    fetchEpisodes: function(){
      fetch("https://breakingbadapi.com/api/episodes")
      .then(res => res.json())
      .then(episodes => this.episodes = episodes)
    },
    fetchCharacters: function() {
        fetch("https://breakingbadapi.com/api/characters")
        .then(res => res.json())
        .then(data => this.characters = data);
        
    }


  },
  components: {
    'episode-list': EpisodeList,
    'episode-detail': EpisodeDetail,
    'app-header': AppHeader,

  }

}
</script>

<style>
.main-container {
  display: flex;
  justify-content: space-between;
}
</style>
