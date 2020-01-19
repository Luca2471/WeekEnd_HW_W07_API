<template lang="html">

</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'teams-names-list',
  props: ['teamsNames'],
  data() {
    return{
      selectedTeamName: ""
    }
  },
  methods: {
    handleCLick(){
      eventBus.$emit('team-selected', this.selectedTeamName)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
