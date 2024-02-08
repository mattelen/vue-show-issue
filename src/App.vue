<script>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
export default {
  name: "VShowBug",
  components:{TheWelcome, HelloWorld},
  data() {
    return {
      showStuff: true,
    }
  },
  computed: {
    optimizedHeight() {
      return 10;
    }
  },
}
</script>

<template>
  <header>
<!--    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125"/>-->
    <button @click="showStuff = !showStuff">Click me to toggle</button>
    <br/>
    State of `showStuff`: {{showStuff}}
    <div class="wrapper" v-show="showStuff" :style="{ maxHeight: optimizedHeight + 'px' }">
      <HelloWorld msg="You did it!"/>
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
