<template lang="html">
    <body>
      <div>
        <h1>NFL Teams By Number Of arrests</h1>
        <div>
          <teams-list :teams="teams"></teams-list>
          <div2>
            <team-details :team='selectedTeam'></team-details>
            <favourite-teams :favouriteTeams="favouriteTeams"></favourite-teams>
          </div2>
        </div>
      </div>
    </body>

</template>

<script>
import { eventBus } from './main.js';
import TeamsList from './components/TeamsList.vue';
import TeamDetails from './components/TeamDetails.vue';
import FavouriteTeams from './components/FavouriteTeams.vue';
// import TotalArrests from './components/TotalArrests/vue';

export default {
  name: 'app',
  data() {
    return {
      teams: [],
      selectedTeam: null,
      favouriteTeams: [],
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
    "favourite-teams": FavouriteTeams,
    // "total-arrests": TotalArrests

  }

}
</script>

<style lang="css" scoped>

body {
  background-image: url("../public/NFLbackground.jpg");
  background-repeat: repeat-x;
  background-size: cover;
  background-clip: border-box;
  color: white;
}

h1 {
  text-align: center;
  font-family: Arial, sans-serif;
    font-size: 4em;
    font-weight: bold;
    position: relative;
    z-index: 1;
    display: inline-block;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-family: Impact, sans-serif;
   color: #24c0fd;
   -webkit-text-stroke: 0.01em #0000aa;
   filter: progid:DXImageTransform.Microsoft.Glow(Color=#0000aa,Strength=1);
   text-shadow: 0.13em -0.13em 0px #0000aa;
   letter-spacing: -0.05em;

}

team-detail {
  width: 90%;
}

favourite-teams {
  width: 40%;
}

</style>
