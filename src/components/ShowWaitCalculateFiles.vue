<template>
  <div class='wait-box'>
      <ul id='item-box'>
          <li v-for="item in waitCalculateFiles" :key="item.name">
              {{item.name}}
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    name: 'ShowWaitCalculateFiles',
    props: {
        waitCalculateFiles: []
    },
}
</script>

<style>
.wait-box {
    width: 400px;
    margin: 20px auto auto;
    border-radius: 10px;
    text-align: center;
    color: blue;
    padding: 10px;
    border: 1px solid rgb(80, 153, 237);
    background-color: rgb(255, 255, 255);
    transition: all 1s ease 0s;
    display: block;
}

#item-box {
    list-style: none;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0px;
}
</style>