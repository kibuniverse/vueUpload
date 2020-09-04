<template>
  <div class="input-box">
    <input class="input-el" type="file" @change="changed" multiple />
  </div>
</template>

<script>
export default {
  name: "Upload",
  props: {
    addFile: {
      type: Function,
      default: null,
    },
  },
  methods: {
    changed(e) {
      console.log(e.target.files);
      if (this.addFile) {
        this.addFile(e.target.files);
      }
    },
  },
};
</script>

<style>
.input-box {
  width: 400px;
  border: 2px dashed gray;
  border-radius: 2%;
  position: relative;
  background-color: rgb(249, 249, 249);
  margin: 100px auto 20px;
  background-image: url(http://49.234.79.241:8001/ddad1a4c0164ed53590ffeb51d0a1a72.png);
  background-size: cover;
}
.input-el {
  width: 400px;
  height: 200px;
  opacity: 0;
}
</style>