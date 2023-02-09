<script>
export default {
  data() {
    return {
      pickedTea:'',
      pickedSirup:'',
      pickedTopping:'',
      teas: [{ flavour: 'black tea' }, { flavour: 'green tea' }, {flavour:'rooibos'}],
      sirups: [{ flavour: 'peach'}, {flavour: 'chocolate'}, {flavour: 'citrus'}],
      toppings: [{flavour: 'tapioca'}, {flavour: 'cherry'}, {flavour: 'yoghurt'}],

    }
  }
}
</script>

<template>

<div class="">Pick a tea</div>
  <template v-for="tea in teas">
    <input type="radio" :id="tea.flavour" :value="tea.flavour" name="tea" v-model="pickedTea" />
	  <label :for="tea.flavour"> {{tea.flavour}}</label>
  </template>

  <div class="">Pick a sirup</div>
  <template v-for="sirup in sirups">
    <input type="radio" :id="sirup.flavour" :value="sirup.flavour" name="sirup" v-model="pickedSirup" />
	  <label :for="sirup.flavour"> {{sirup.flavour}}</label>
  </template>

  <div class="">Pick a topping</div>
  <template v-for="topping in toppings">
    <input type="radio" :id="topping.flavour" :value="topping.flavour" name="topping" v-model="pickedTopping" />
	  <label :for="topping.flavour"> {{topping.flavour}}</label>
  </template>

<!-- result -->
<div class="">Your bubble tea :  {{ pickedTea }} +  {{ pickedSirup }} sirup +  {{ pickedTopping }} topping !</div>

</template>