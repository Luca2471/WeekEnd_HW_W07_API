<template lang="html">
  <body>
    <h1>NFL Teams Arests</h1>
  </body>

</template>

<script>
import {eventBus} from './main.js';
import TeamsNamesList from './components/TeamsNamesList.vue'

export default {
  name: 'app',
  data(){
    return {
      teams: [],
      teamsNames: []
    }
  },

  mounted(){
    fetch('http://nflarrest.com/api/v1/team')
      .then(result => result.json())
      .then(teams => {
        this.teamsNames = teams.map(team => team.Team_preffered_name)
        this.teams = teams
      })
  },
  
  components: {
    "teams-names-list": TeamsNamesList
  }

}
</script>

<style lang="css" scoped>
</style>
