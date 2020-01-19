<template lang="html">
  <div v-if="!favouriteTeams.length == 0">
    <ul>
      <h3>Bookmarked Teams</h3>
      <li v-for="team in favouriteTeams">{{ team.Team_preffered_name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'favourite-teams',
  props: ['favouriteTeams']
}
</script>

<style lang="css" scoped>
</style>
