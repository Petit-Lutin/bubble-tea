<script>
export default {
  data() {
    return {
      pickedTea:'',
      pickedSirup:'',
      pickedTopping:'',
      teas: [{ flavour: 'black tea' , color: 'brown'}, { flavour: 'green tea' , color:'green'}, {flavour:'rooibos', color:'orange'}],
      sirups: [{ flavour: 'peach'}, {flavour: 'chocolate'}, {flavour: 'citrus'}],
      toppings: [{flavour: 'tapioca'}, {flavour: 'cherry'}, {flavour: 'yoghurt'}],
      teaColor:'black'

    }
  },
    methods: {
      getTeaColor(event){
        //console.log(event.target.getAttribute('data-color'))
        this.teaColor = event.target.getAttribute('data-color');

      }
    }
}
</script>

<template>

<div class="">Pick a tea</div>
  <template v-for="tea in teas">
    <input @click="getTeaColor" type="radio" :id="tea.flavour" :value="tea.flavour" :data-color="tea.color" name="tea" v-model="pickedTea" />
	  <span :style="{ 'color': tea.color}"><label :for="tea.flavour"> {{tea.flavour}}</label></span>
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

<div class="">
  <br> Your bubble tea : <span :style="{ 'color': teaColor}" v-if="pickedTea">{{ pickedTea }}</span>   <span v-if="pickedSirup">+ {{ pickedSirup }} sirup</span> 
  <span v-if="pickedTopping">+  {{ pickedTopping }} topping ! </span>

  <div class="resultTea" style="width:150px;height:300px">
    <div class="resultSirup" style="width:150px;height:200px"></div>
    <div class="resultTopping" style="width:150px;height:75px"></div>

  </div>

</div>

</template>

<style scoped>
.resultTea{
  /*  */
}

</style>