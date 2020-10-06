<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <UploadBox :addFile="addFile" />
    <ShowWaitCalculateFiles :waitCalculateFiles='waitCalculateFiles' />

  </div>
</template>

<script>
import UploadBox from "./components/Upload.vue";
import UploadTool from 'upload-tool'
import ShowWaitCalculateFiles from './components/ShowWaitCalculateFiles'
export default {
  name: "App",
  components: {
    UploadBox,
    ShowWaitCalculateFiles,
  },
  data () {
    return {
      waitCalculateFiles: [],
      waitUploadFile: [],
      UploadedFiles: [],
      uploadTool: new UploadTool({
        concurrency: 3,
        chunkSize: 3*1024*1024,
        updateWaitCalculateFile: this.updateWaitCalculateFile,
        updateWaitUploadFile: this.updateWaitUploadFile,
        updateUploadedFiles: this.updateUploadedFiles
      })
    }
  },
  methods: {
    addFile(files) {
      this.uploadTool.updateWaitCalculateFile(files)
    },
    updateWaitCalculateFile(waitCalculateFiles) {
      console.log(waitCalculateFiles)
      this.waitCalculateFiles = waitCalculateFiles
    },
    updateWaitUploadFile(waitUploadFiles) {
      this.waitUploadFile = waitUploadFiles
      console.log(waitUploadFiles)
    },
    updateUploadedFiles(uploadedFiles) {
      this.uploadedFiles = uploadedFiles
      console.log(uploadedFiles)
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
