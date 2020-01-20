<template lang="html">
  <body1>
    <span>
<div v-if='team'>
  <h4>Team: {{ team.Team_name }}</h4>
  <p>City: {{ team.Team_city }}</p>
  <p>Arrest Count: {{ team.arrest_count }}</p>
  <p>Conference division: {{ team.Team_Conference_Division}}</p>
  <div>
    <button v-on:click="addToFavourites">add to Bookmarks!</button>
  </div>
</div>
</span>

</body1>


</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'team-details',
  props: ['team'],
  methods: {
    addToFavourites() {
      eventBus.$emit('favourite-added', this.selectedTeam)
    }
  }
}
</script>

<style lang="css" scoped>
  span {
    font-size: 30px;
    font-family: "Times New Roman", Times, serif;
    list-style: none;
    padding:5px;
    padding-top: 20px;
    color: purple;
    text-align: right;
    display: grid;
    vertical-align: text-top;
    position: absolute;
    top: 20px;
    right: 16px;

  }


</style>
