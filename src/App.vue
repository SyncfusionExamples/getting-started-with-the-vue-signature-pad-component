<template>
  <div id="actionBtn">
    <ejs-button v-on:click="saveSign">Save</ejs-button>
    <ejs-button v-on:click="clearSign">Clear</ejs-button>
    <ejs-button v-on:click="undoSign">Undo</ejs-button>
    <ejs-button v-on:click="redoSign">Redo</ejs-button>
  </div>
  <ejs-signature ref="signObj" :backgroundColor="bgColor"
    :strokeColor="customStrokeColor"
    velocity="1"
    minStrokeWidth="2"
    maxStrokeWidth="5"
    ></ejs-signature>
    <!-- backgroundImage="https://www.syncfusion.com/blogs/wp-content/uploads/2019/11/blog_1x.jpg" -->
    <!-- disabled="true" -->
</template>

<script>
import {SignatureComponent} from '@syncfusion/ej2-vue-inputs';
import {ButtonComponent} from '@syncfusion/ej2-vue-buttons';
export default {
  name: 'App',
  components: {
    'ejs-signature': SignatureComponent,
    'ejs-button': ButtonComponent
  },
  data(){
    return{
      bgColor: 'red',
      customStrokeColor: 'white'
    }
  },
  methods:{
    saveSign(){
      this.$refs.signObj.ej2Instances.save("jpg","Signature");
    },
    clearSign(){
      this.$refs.signObj.ej2Instances.clear();
    },
    undoSign(){
      this.$refs.signObj.ej2Instances.undo();
    },
    redoSign(){
      this.$refs.signObj.ej2Instances.redo();
    }
  }
}
</script>

<style>
@import url("https://cdn.syncfusion.com/ej2/bootstrap5.css");
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#actionBtn .e-btn{
  margin: 2%;
}
</style>
