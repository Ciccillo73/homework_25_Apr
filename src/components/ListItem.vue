<template lang="html">
  <div>
   <li v-on:click="handleClick">{{episode.episode_id}}</li>
   


  </div>
</template>


<script>

import {eventBus} from '../main.js';

export default {
  name: 'list-item',
  props: ['episode'],
  methods: {
    handleClick: function() {
      eventBus.$emit('episode-selected', this.episode)
    }
  }
}
</script>

<style lang="css" scoped>
li {
    color:red;
    width: 40vw;
    list-style-type: none;
    display: block;
    background: #000;
    font-size: 20px;
    margin: 2px 0;
    padding: 5px;
    cursor: pointer;
    transition: 0.2s all ease-in;
    text-align: center;
    font-family:cursive;
  }

  li:hover {
    background: #dbe8ff;
    color: #222;
  }

</style>
