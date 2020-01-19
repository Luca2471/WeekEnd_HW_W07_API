<template lang="html">
    <body>
      <div>
        <h1>NFL Teams By Number Of arrests</h1>
        <div>
          <teams-list :teams="teams"></teams-list>
          <team-details :team='selectedTeam'></team-details>
        </div>
      </div>
    </body>

</template>

<script>
import { eventBus } from './main.js';
import TeamsList from './components/TeamsList.vue';
import TeamDetails from './components/TeamDetails.vue';

export default {
  name: 'app',
  data() {
    return {
      teams: [],
      selectedTeam: ""
    };
  },
  mounted() {
    fetch('http://nflarrest.com/api/v1/team')
      .then(result => result.json())
      .then(teams => this.teams = teams)

      eventBus.$on('team-selected', (team) => {
        this.selectedTeam = team
      })
  },

  components: {
    "teams-list": TeamsList,
    "team-details": TeamDetails
  }

}
</script>

<style lang="css" scoped>
</style>
