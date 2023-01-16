<template>
  <div class="container mt-5 text-center fw-bold">
    <h2 class="mb-5">Dynamic Components Example</h2>
    <div class="row mb-5">
      <div class="col">
        <button @click="changeActiveComponent('RedComponent')" class="btn btn-danger">Red</button>
      </div>
      <div class="col">
        <button @click="changeActiveComponent('GreenComponent')" class="btn btn-success">Green</button>
      </div>
      <div class="col">
        <button @click="changeActiveComponent('BlueComponent')" class="btn btn-primary">Blue</button>
      </div>
    </div>
    <component :is="activeComponent"></component>
    
  </div>
</template>
<script>
import RedComponent from "@/components/RedComponent.vue";
import GreenComponent from "@/components/GreenComponent.vue";
import BlueComponent from "@/components/BlueComponent.vue";

export default {
  components: {
    RedComponent,
    GreenComponent,
    BlueComponent
  },
  data(){
    return {
      activeComponent : 'RedComponent',
      components : ['RedComponent', 'GreenComponent', 'BlueComponent']
    }
  },
  methods: {
    changeActiveComponent : function(component){
      this.activeComponent = component;
    }
  }
};
</script>
