<template lang="html">
  <div>
    <ul>
      <list-item v-for='team in teams' :team="team" ></list-item>
    </ul>
  </div>
</template>

<script>
import ListItem from './ListItem.vue';

export default {
  name: 'teams-list',
  props: ['teams'],
  components: {
    'list-item': ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
