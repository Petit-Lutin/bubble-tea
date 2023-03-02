<script>
export default {
  data() {
    return {
      teas: [{ flavour: 'Black tea' , color: 'brown'}, { flavour: 'Green tea' , color:'green'}, {flavour:'Rooibos', color:'orange'}],
      sirups: [{ flavour: 'Peach', color:'#db6277'}, {flavour: 'Chocolate', color:'chocolate'}, {flavour: 'Citrus', color:'yellow'}],
      toppings: [{flavour: 'Tapioca', color:'light brown'}, {flavour: 'Cherry', color:'red'}, {flavour: 'Yoghurt', color:'wheat'}],
      pickedTea:'',
      pickedSirup:'',
      pickedTopping:'',
      teaColor:'',
      sirupColor:'',
      toppingColor:'',
      finished:false
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
    },
    computed: {
      isTeaSelected() {
        if (this.pickedTea != ''){
          return true;
        }
    },
    isSirupAfterTeaSelected() {
        if (this.pickedTea != '' && this.pickedSirup != ''){
          return true;
        }
    }, 
    isToppingAfterSirupAndTeaSelected() {
        if (this.pickedTea != '' && this.pickedSirup != '' && this.pickedTopping != ''){
          return true;
        }
    },
  }
}
</script>

<template>

<div class="bubble-tea">
  <div class="menu">
    <div class="ingredient">1. Pick a tea <span v-if="pickedTea"><i class="fa fa-check" aria-hidden="true"></i></span>
      <div class="pick">
        <template v-for="tea in teas">
          <input type="radio" :id="tea.flavour" :value="tea.flavour" :data-color="tea.color" name="tea" v-model="pickedTea" @click="getTeaColor"/>
            <label :for="tea.flavour"> {{tea.flavour}}
              <span :style="{ 'color': tea.color }">
                <i class="fa fa-circle" aria-hidden="true"></i>
              </span>
            </label>
        </template>
      </div>
    </div>
      <div class="ingredient">2. Pick a sirup <span v-if="pickedSirup"><i class="fa fa-check" aria-hidden="true"></i></span>
      <div class="pick">
        <template v-for="sirup in sirups">
          <input type="radio" :id="sirup.flavour" :value="sirup.flavour" :data-color="sirup.color" name="sirup" v-model="pickedSirup" @click="getSirupColor"/>
            <label :for="sirup.flavour"> {{sirup.flavour}}
              <span :style="{ 'color': sirup.color}">
                <i class="fa fa-circle" aria-hidden="true"></i>
              </span>
            </label>
        </template>
      </div>
    </div>
      <div class="ingredient">3. Pick a topping <span v-if="pickedTopping"><i class="fa fa-check" aria-hidden="true"></i></span>
      <div class="pick">
        <template v-for="topping in toppings">
          <input type="radio" :id="topping.flavour" :value="topping.flavour" :data-color="topping.color"  name="topping" v-model="pickedTopping" @click="getToppingColor"/>
            <label :for="topping.flavour"> {{topping.flavour}}
              <span :style="{ 'color': topping.color}">
                <i class="fa fa-circle" aria-hidden="true"></i>
              </span>
            </label>
        </template>
      </div>
    </div>
  

    <div class="text-result" v-if="isTeaSelected">
  
      <div class="">
        Your bubble tea : <br>
        <span :style="{ 'color': teaColor}" v-if="isTeaSelected">{{ pickedTea }}</span>   <span :style="{ 'color': sirupColor}" v-if="isSirupAfterTeaSelected"  > + {{ pickedSirup }} sirup</span>
          <span :style="{ 'color': toppingColor}" v-if="isToppingAfterSirupAndTeaSelected" >  +  {{ pickedTopping }} topping ! </span>
      </div>

        <button v-if="isToppingAfterSirupAndTeaSelected" @click="finished=true">Order <i class="fa fa-check" aria-hidden="true"></i>
      </button>

      </div>
  </div>
  
  <div class="result-panel">
  <!-- result -->

  
    <div class="illustrated-result">
  
    <svg
      xmlns:dc="http://purl.org/dc/elements/1.1/"
      xmlns:cc="http://creativecommons.org/ns#"
      xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
      xmlns:svg="http://www.w3.org/2000/svg"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
      xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
      version="1.1"
      id="svg2"
      xml:space="preserve"
      width="130"
    
      viewBox="0 0 155.98894 334.95495"
      sodipodi:docname="bubbletea_final.svg"
      inkscape:version="0.92.1 r15371"><title
        id="title4682">Bubble Tea</title><metadata
        id="metadata8"><rdf:RDF><cc:Work
            rdf:about=""><dc:format>image/svg+xml</dc:format><dc:type
              rdf:resource="http://purl.org/dc/dcmitype/StillImage" /><dc:title>Bubble Tea</dc:title><dc:date>10 february 2023</dc:date><dc:creator><cc:Agent><dc:title>Petit Lutin (Laurence Platzer)</dc:title></cc:Agent></dc:creator><cc:license
              rdf:resource="http://creativecommons.org/licenses/by-sa/4.0/" /></cc:Work><cc:License
            rdf:about="http://creativecommons.org/licenses/by-sa/4.0/"><cc:permits
              rdf:resource="http://creativecommons.org/ns#Reproduction" /><cc:permits
              rdf:resource="http://creativecommons.org/ns#Distribution" /><cc:requires
              rdf:resource="http://creativecommons.org/ns#Notice" /><cc:requires
              rdf:resource="http://creativecommons.org/ns#Attribution" /><cc:permits
              rdf:resource="http://creativecommons.org/ns#DerivativeWorks" /><cc:requires
              rdf:resource="http://creativecommons.org/ns#ShareAlike" /></cc:License></rdf:RDF></metadata><defs
        id="defs6" /><sodipodi:namedview
        pagecolor="#ffffff"
        bordercolor="#666666"
        borderopacity="1"
        objecttolerance="10"
        gridtolerance="10"
        guidetolerance="10"
        inkscape:pageopacity="0"
        inkscape:pageshadow="2"
        inkscape:window-width="1920"
        inkscape:window-height="1017"
        id="namedview4"
        showgrid="false"
        inkscape:zoom="1.1559561"
        inkscape:cx="90.31183"
        inkscape:cy="152.46427"
        inkscape:window-x="-8"
        inkscape:window-y="-8"
        inkscape:window-maximized="1"
        inkscape:current-layer="layer1"
        fit-margin-top="0"
        fit-margin-left="0"
        fit-margin-right="0"
        fit-margin-bottom="0" /><g
  
        inkscape:groupmode="layer"
        id="layer2"
        inkscape:label="tea" v-if="isTeaSelected"
        style="display:inline"
        transform="translate(-304.37316,-318.89494)"><path class="backgroundTea"
        :style="{ 'fill': teaColor}" style="display:inline;filter:brightness(65%);/*fill:#00a476;*/fill-opacity:1;stroke:none;stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1"
          d="m 310.7817,463.03662 c 17.38709,-18.22071 143.67582,-8.60799 143.41097,0.0366 l -3.21146,16.21025 -111.63658,12.38707 -25.69171,-8.41098 z"
          id="path4501"
          inkscape:connector-curvature="0"
          sodipodi:nodetypes="cccccc" /><path class="mainTea"
          :style="{ 'fill': teaColor}" style="/*fill:#76ccb2;*/fill-opacity:1;stroke:none;stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1"
          d="m 310.7817,463.03662 c -0.42988,6.43742 7.02047,24.05465 37.58354,11.13027 26.27143,-11.10954 37.79617,8.13829 60.25778,-1.77842 10.6361,-4.69579 36.44688,4.32954 45.11394,-6.97287 l -25.70739,177.41658 c -0.22952,13.14319 -90.03971,12.90893 -93.67431,-0.0742 z"
          id="path4499"
          inkscape:connector-curvature="0"
          sodipodi:nodetypes="csscccc" /></g><g v-if="isSirupAfterTeaSelected"
        style="display:inline"
        inkscape:label="sirup"
        id="g4510"
        inkscape:groupmode="layer"
        transform="translate(-304.37316,-318.89494)"><path class="backgroundSirup"
          sodipodi:nodetypes="cccccc"
          inkscape:connector-curvature="0"
          id="path4506"
          d="m 324.19051,558.93173 c 12.53265,-11.66912 114.27934,-3.11828 115.07952,0.0434 l -2.57701,19.2219 -89.58231,14.68843 -20.6162,-9.97363 z"
          :style="{ 'fill': sirupColor}" style="display:inline;filter:brightness(65%);/*fill:#a867a4;*/fill-opacity:1;stroke:none;stroke-width:0.97546393px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1" /><path class="mainSirup"
          sodipodi:nodetypes="cscccc"
          inkscape:connector-curvature="0"
          id="path4508"
          d="m 323.80277,560.08735 c -0.42988,3.2223 8.62198,6.2846 24.56247,7.63274 23.94208,2.02485 46.76545,11.78242 90.88155,-7.30647 l -11.21722,82.41856 c 3.28293,12.51376 -86.60729,12.28123 -92.59295,1.80996 z"
          :style="{ 'fill': sirupColor}" style="/*fill:#e8c1e6;*/fill-opacity:1;stroke:none;stroke-width:0.70750135px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1" /></g><g v-if="pickedTea"
        inkscape:groupmode="layer"
        id="layer1"
        inkscape:label="cup"
        transform="translate(-304.37316,-318.89494)"
        style="display:inline"><g
          id="g4725"><path
            sodipodi:nodetypes="cc"
            inkscape:connector-curvature="0"
            id="path4496"
            d="m 334.35526,642.75798 c -1.177,-17.93225 97.80176,-14.29968 93.67431,0.0742"
            style="fill:none;stroke:#73747d;stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1" /><path
            sodipodi:nodetypes="ccccc"
            inkscape:connector-curvature="0"
            id="path4492"
            d="m 334.35526,642.75798 c 1.12617,10.03962 85.22608,16.45837 93.67431,0.0742 L 459.36001,423.02644 C 460.02757,401.2794 305.92406,401.0015 305.37492,421.29627 Z"
            style="fill:none;stroke:#000000;stroke-width:2;stroke-linecap:butt;stroke-linejoin:miter;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1" /><path
            sodipodi:nodetypes="cc"
            inkscape:connector-curvature="0"
            id="path4494"
            d="m 305.37492,421.29628 c 15.96953,20.02958 150.94753,18.36412 153.98509,1.73017"
            style="fill:none;stroke:#000000;stroke-width:2;stroke-linecap:butt;stroke-linejoin:miter;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1" /></g></g><g
        inkscape:groupmode="layer"
        id="layer4"
        inkscape:label="toppings" v-if="isToppingAfterSirupAndTeaSelected"
        transform="translate(-304.37316,-318.89494)"
        :style="{ 'fill': toppingColor}"
        style="display:inline"><g
          id="g4720"><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="602.099"
            cx="348.62915"
            id="path4513"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="596.57831"
            cx="384.15219"
            id="path4513-5"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="617.68219"
            cx="363.96585"
            id="path4513-2"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="608.96533"
            cx="374.82367"
            id="path4513-9"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="612.33612"
            cx="397.45682"
            id="path4513-4"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="631.45197"
            cx="344.62933"
            id="path4513-7"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="620.74078"
            cx="383.18018"
            id="path4513-5-4"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="640.97955"
            cx="354.99179"
            id="path4513-2-4"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="632.2627"
            cx="368.66116"
            id="path4513-9-8"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="639.09381"
            cx="394.75464"
            id="path4513-4-0"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            transform="rotate(94.223735)"
            ry="4.2713556"
            rx="4.3254237"
            cy="-461.211"
            cx="554.66705"
            id="path4513-6"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            transform="rotate(94.223735)"
            ry="4.2713556"
            rx="4.3254237"
            cy="-466.73169"
            cx="590.19012"
            id="path4513-5-6"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            transform="rotate(94.223735)"
            ry="4.2713556"
            rx="4.3254237"
            cy="-445.62781"
            cx="570.00378"
            id="path4513-2-0"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            transform="rotate(94.223735)"
            ry="4.2713556"
            rx="4.3254237"
            cy="-454.34467"
            cx="580.86157"
            id="path4513-9-0"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            transform="rotate(94.223735)"
            ry="4.2713556"
            rx="4.3254237"
            cy="-461.16022"
            cx="606.48376"
            id="path4513-4-5"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="629.29218"
            cx="358.16992"
            id="path4513-1"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="623.55524"
            cx="394.55804"
            id="path4513-5-7"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="644.87537"
            cx="373.50662"
            id="path4513-2-07"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="636.15851"
            cx="384.36444"
            id="path4513-9-9"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="635.85266"
            cx="406.99759"
            id="path4513-4-1"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="598.3653"
            cx="336.75906"
            id="path4513-69"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="594.57477"
            cx="369.03802"
            id="path4513-5-3"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="615.67865"
            cx="348.85168"
            id="path4513-2-7"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="606.96179"
            cx="359.7095"
            id="path4513-9-1"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /><ellipse
            ry="4.2713556"
            rx="4.3254237"
            cy="607.52106"
            cx="384.72165"
            id="path4513-4-50"
            style="opacity:0.98999999;/*fill:#803541;*/fill-opacity:1;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;paint-order:fill markers stroke" /></g></g><g
        inkscape:groupmode="layer"
        id="layer5"
        inkscape:label="straw" v-if="finished"
        style="display:inline;opacity:1"
        transform="translate(-304.37316,-318.89494)"><g
          id="g4693"><path
            sodipodi:nodetypes="cc"
            inkscape:connector-curvature="0"
            id="path4674"
            d="m 378.66027,322.35221 c 1.31877,3.10366 14.77799,2.97635 15.63845,0.27349"
            style="fill:none;stroke:#000000;stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1" /><path
            sodipodi:nodetypes="cc"
            inkscape:connector-curvature="0"
            id="path4676"
            d="m 370.76992,596.74628 c 1.81986,-4.19521 14.20374,-3.91813 15.22408,-0.10813"
            style="fill:none;stroke:#000000;stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1" /><path
            sodipodi:nodetypes="cccc"
            inkscape:connector-curvature="0"
            id="path4678"
            d="m 459.36001,423.02644 c -0.36181,10.20433 -74.14624,14.99011 -119.5566,9.92017 -9.84908,-1.60949 -33.15329,-4.78534 -33.96227,-12.80007 5.77265,-18.11516 144.50204,-20.08259 153.51887,2.8799 z"
            style="fill:#c7c2c2;fill-opacity:1;stroke:#000000;stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1" /><path
            sodipodi:nodetypes="ccccc"
            inkscape:connector-curvature="0"
            id="path4672"
            d="m 378.66027,322.35221 -7.97145,274.12373 c 0.55048,4.63622 14.90659,4.17835 15.30518,0.16221 l 8.29031,-273.96153 c 0.36007,-4.28963 -15.50262,-4.06741 -15.62404,-0.32441 z"
            style="fill:none;stroke:#000000;stroke-width:1.21422517px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1" /><g
            id="g4685"><path
              style="fill:none;stroke:#000000;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
              d="m 371.87981,420.17722 c 4.40246,2.17188 21.86571,1.61511 24.60201,0.65379"
              id="path4680"
              inkscape:connector-curvature="0"
              sodipodi:nodetypes="cc" /></g></g></g></svg>
  
    </div>
  </div>
</div>

</template>

<style scoped>


.menu{
  padding: 15px;
  border-radius: 10px;  
  background: #f9e7f5;
  min-height:390px;
}
.ingredient{
  margin-bottom: 20px;
}
.pick
{
  padding-top: 5px;
  display:flex;
  justify-content: space-between;
  flex:100%;
}
.pick label, button{
  padding:5px 10px;
  background:  #fbb5e0;
  margin-right: 5px;
  border-radius: 5px;
  cursor: pointer;
}

button{
  padding:8px 15px;
  border-radius: 5px;
  border:1px solid #fbb5e0;
  /* box-shadow: ; */

}

button:hover, button:active{
  background: #ca75a9;
  border:1px solid #ca75a9;

}
.pick label:hover, .pick input[type="radio"]:checked+label{
  background: #ca75a9;
  color:white;
}
input[type=radio]{
  display:none;
}
.pick input[type="radio"]+label .fa.fa-circle{
  display: inline;
  font-size:0.8em;
}

.pick input[type="radio"]+label .fa.fa-check{
  display: none;
}
.pick input[type="radio"]:checked+label .fa.fa-circle{
  /* display: none; */
}

/* .pick input[type="radio"]:checked+label .fa.fa-check{
  display: inline;
  font-size:1.7em;
} */

.menu .fa.fa-check{
  color:green;
  font-size: 1.2em;
}

.result-panel{
  display: flex;
  flex-direction: column;
}
.text-result{
  height:100px;
}

.illustrated-result{
  text-align: center;
}
</style>