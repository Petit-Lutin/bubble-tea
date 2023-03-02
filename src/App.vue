<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import Choices from './components/Choices.vue'
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" /> -->

    <!-- <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div> -->
        <h2>Order your bubble tea! </h2> <img src="/public/bubbletea_final.svg" width="25">
  </header>

  <main>
    <!-- <TheWelcome /> default-->
    <Choices />
    
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  padding-bottom: 10px;

}

.logo {
  display: block;
  margin: 0 auto 2rem;
}



@media (min-width: 1024px) {
  header {
    /* display: flex;
    place-items: center; */
    width: 50%;
    /* justify-content: space-between;
    align-items: baseline; */
    /* padding-right: calc(var(--section-gap) / 2); */
  }

  .bubble-tea{
    display: grid;
    grid-template-columns: repeat(2,1fr);
    gap: 20px;
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
