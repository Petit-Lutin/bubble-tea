<script>
export default {
  data() {
    return {
      //picked: 'One',
      pickedTea:'',
      pickedSirup:'',
      pickedBobba:'',
      teas: [{ flavour: 'black' }, { flavour: 'green' }, {flavour:'rooibos'}],
      sirups: [{ flavour: 'peach'}, {flavour: 'chocolate'}, {flavour: 'citrus'}],
      toppings: [{flavour: 'tapioca'}, {flavour: 'cherry'}, {flavour: 'yoghurt'}],

    }
  }
}
</script>

<template>


  <li v-for="tea in teas">
  {{ tea.flavour }}
</li>

<li v-for="sirup in sirups">
  {{ sirup.flavour }}
</li>

<li v-for="topping in toppings">
  {{ topping.flavour }}
</li>
<div class="">Pick a tea</div>
<div>Picked: {{ pickedTea }}</div>
  <template v-for="tea in teas">
    
    <input type="radio" :id="tea.flavour" :value="tea.flavour" name="tea" v-model="pickedTea" />
	<label :for="tea.flavour"> {{tea.flavour}}</label>
  </template>







<div>Picked: {{ picked }}</div>
	<input type="radio" id="one" value="One" v-model="picked" />
	<label for="one">One</label>

	<input type="radio" id="two" value="Two" v-model="picked" />
	<label for="two">Two</label>
</template>