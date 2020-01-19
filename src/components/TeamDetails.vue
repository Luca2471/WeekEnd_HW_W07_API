<template lang="html">
<div v-if='team'>
  <h4>Team: {{ team.Team_name }}</h4>
  <p>City: {{ team.Team_city }}</p>
  <p>Arrest Count: {{ team.arrest_count }}</p>
  <p>Conference division: {{ team.Team_Conference_Division}}</p>
  <div>
    <button v-on:click="addToFavourites">add to favourites!</button>
  </div>
</div>

</template>

<script>
import { eventBus } from '../main.js'

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
</style>
