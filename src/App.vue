<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <UploadBox :addFile="addFile" />
    
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import UploadBox from "./components/Upload.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    UploadBox,
  },
  data () {
    return {
      waitCalculated: []
    }
  },
  methods: {
    addFile(files) {
      for(let i = 0, len = files.length; i < len; i++) {
        this.waitCalculated.push(files[i])
      }
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
