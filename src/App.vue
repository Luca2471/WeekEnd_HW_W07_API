<template lang="html">
    <body>
      <div>
        <h1>NFL Teams By Number Of arrests</h1>
        <div>
          <teams-list :teams="teams"></teams-list>
          <div>
            <team-details :team='selectedTeam'></team-details>
            <favourite-teams :favouriteTeams="favouriteTeams"></favourite-teams>
          </div>
        </div>
      </div>
    </body>

</template>

<script>
import { eventBus } from './main.js';
import TeamsList from './components/TeamsList.vue';
import TeamDetails from './components/TeamDetails.vue';
import FavouriteTeams from './components/FavouriteTeams.vue';

export default {
  name: 'app',
  data() {
    return {
      teams: [],
      selectedTeam: null,
      favouriteTeams: []
    };
  },
  mounted() {
    fetch('http://nflarrest.com/api/v1/team')
      .then(result => result.json())
      .then(teams => this.teams = teams)

      eventBus.$on('team-selected', (team) => {
        this.selectedTeam = team
      })

      eventBus.$on('favourite-added', (selectedTeam) => {
        this.favouriteTeams.push(selectedTeam)
      })
  },

  components: {
    "teams-list": TeamsList,
    "team-details": TeamDetails,
    "favourite-teams": FavouriteTeams

  }

}
</script>

<style lang="css" scoped>
</style>
