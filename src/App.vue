<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/spells">Spells</router-link> |
      <router-link to="/items">Items</router-link> | 
      <router-link to="/monsterchanger">2e Monster Changer</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
import spellsModel from './models/spells';
import itemsModel from './models/items';
import monstersModel from './models/monsters';

export default {
    name: 'App',
    data() {
        return {

        };
    },
    mounted() {
        spellsModel.loadSpells();
        itemsModel.loadItems();
        monstersModel.loadMonsterNames();
    }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
