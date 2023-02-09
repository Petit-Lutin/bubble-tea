<script>
export default {
  data() {
    return {
      teas: [{ flavour: 'black tea' , color: 'brown'}, { flavour: 'green tea' , color:'green'}, {flavour:'rooibos', color:'orange'}],
      sirups: [{ flavour: 'peach', color:'pink'}, {flavour: 'chocolate', color:'chocolate'}, {flavour: 'citrus', color:'yellow'}],
      toppings: [{flavour: 'tapioca', color:'light brown'}, {flavour: 'cherry', color:'red'}, {flavour: 'yoghurt', color:'wheat'}],
      pickedTea:'',
      pickedSirup:'',
      pickedTopping:'',
      teaColor:'',
      sirupColor:'',
      toppingColor:''
    }
  },
    methods: {
      getTeaColor(event){
        //console.log(event.target.getAttribute('data-color'))
        this.teaColor = event.target.getAttribute('data-color');
      },

      getSirupColor(event){
        //console.log(event.target.getAttribute('data-color'))
        this.sirupColor = event.target.getAttribute('data-color');
      },

      getToppingColor(event){
        //console.log(event.target.getAttribute('data-color'))
        this.toppingColor = event.target.getAttribute('data-color');
      }
    }
}
</script>

<template>

<div class="">Pick a tea</div>
  <template v-for="tea in teas">
    <input type="radio" :id="tea.flavour" :value="tea.flavour" :data-color="tea.color" name="tea" v-model="pickedTea" @click="getTeaColor"/>
	  <span :style="{ 'color': tea.color}"><label :for="tea.flavour"> {{tea.flavour}}</label></span>
  </template>

  <div class="">Pick a sirup</div>
  <template v-for="sirup in sirups">
    <input type="radio" :id="sirup.flavour" :value="sirup.flavour" :data-color="sirup.color" name="sirup" v-model="pickedSirup" @click="getSirupColor"/>
	  <span :style="{ 'color': sirup.color}"><label :for="sirup.flavour"> {{sirup.flavour}}</label></span>
  </template>

  <div class="">Pick a topping</div>
  <template v-for="topping in toppings">
    <input type="radio" :id="topping.flavour" :value="topping.flavour" :data-color="topping.color"  name="topping" v-model="pickedTopping" @click="getToppingColor"/>
	  <span :style="{ 'color': topping.color}"><label :for="topping.flavour"> {{topping.flavour}}</label></span>
  </template>

<!-- result -->

<div class="">
  <br> Your bubble tea : <span :style="{ 'color': teaColor}" v-if="pickedTea">{{ pickedTea }}</span>   <span :style="{ 'color': sirupColor}" v-if="pickedSirup"  >+ {{ pickedSirup }} sirup</span> 
  <span :style="{ 'color': toppingColor}" v-if="pickedTopping" >+  {{ pickedTopping }} topping ! </span>

  <div class="result">
    <div class="resultTea" :style="{ 'background': teaColor}"> </div>
      <div class="resultSirup" :style="{ 'background': sirupColor}"></div>
      <div class="resultTopping" :style="{ 'background': toppingColor}"></div>
  </div>

</div>

</template>

<style scoped>

.result{
  display: flex;
  flex-direction: column;
 justify-content:flex-end;
 width:150px;
 height:300px;

}
.resultTea{
  width:150px;
  height:300px;
}

.resultSirup{
  width:150px;
  height:200px;
}

.resultTopping{
  width:150px;
  height:75px;
}
</style>