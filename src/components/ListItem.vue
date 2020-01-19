
<template lang="html">
  <li v-on:click="handleClick">{{ team.Team_preffered_name }}</li>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'list-item',
  props: ['team'],
  data() {
    return {
      selectedTeamName: ""
    }
  },
  methods: {
    handleClick(){
      eventBus.$emit('team-selected', this.team)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
