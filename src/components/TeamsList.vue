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

div {
  padding-top: 60px;
  font-family: Arial, sans-serif;
    font-size: 0.9em;
    font-weight: bold;
    position: relative;
    z-index: 1;
    display: inline-block;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    transform: scale(1, 1.5);
 -webkit-transform: scale(1, 1.5);
 -moz-transform: scale(1, 1.5);
 -o-transform: scale(1, 1.5);
 -ms-transform: scale(1, 1.5);
 background: red;
  background: -webkit-linear-gradient(left, #b306a9, #ef2667, #f42e2c, #ffa509, #fdfc00, #55ac2f, #0b13fd, #a804af);
  background: -o-linear-gradient(left, #b306a9, #ef2667, #f42e2c, #ffa509, #fdfc00, #55ac2f, #0b13fd, #a804af);
  background: -moz-linear-gradient(left, #b306a9, #ef2667, #f42e2c, #ffa509, #fdfc00, #55ac2f, #0b13fd, #a804af);
  background: linear-gradient(to right, #b306a9, #ef2667, #f42e2c, #ffa509, #fdfc00, #55ac2f, #0b13fd, #a804af);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

</style>
