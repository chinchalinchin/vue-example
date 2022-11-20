<template>
  <header>
    <h1>Caf&eacute; Mark</h1>
  </header>
  <main>
    <nav>
      <Icon :id="element.id"
        :icon="element.icon"
        :dimensions="iconDimensions"
        :route="element.route"
        v-for="element in this.navigation"
      ></Icon>
    </nav>
    <RouterView/>
  </main>
  
</template>

<script>
  import Icon from './components/shared/Icon.vue';

  export default {
    components: {
      Icon,
    },
    data () {
      return {
        navigation: [
          {
            alt: 'view drink menu',
            icon: 'meal_coffee_cup',
            id: 'drink-menu-link',
            route: 'drinks'
          },
          {
            alt: 'view breakfast menu',
            icon: 'meal_breakfast',
            id: 'breakfast-menu-link',
            route: 'breakfast'
          },
          {
            alt: 'view lunch menu',
            icon: 'meal_quesadilla',
            id: 'lunch-menu-link',
            route: 'lunch'
          }
        ],
        iconDimensions: {
          width: '100px',
          height: '100px'
        }
      }
    }
  }
</script>

<script setup>
  import { 
    RouterView 
  } from "vue-router";
</script>

<style scoped>
header {
  height: 15%;
  display: flex;
  flex-direction: row;
  justify-content: center;
}
main {
  min-height: 80%;
  display: flex;
  flex-direction: row;
}
nav {
  box-shadow: var(--shadow-bg1) var(--shadow-bg1) var(--shadow-bg3) black;
  min-height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
</style>
