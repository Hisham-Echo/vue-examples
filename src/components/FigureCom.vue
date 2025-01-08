import { default } from './HelloWorld.vue';
<template>
  <div>
    <img src="../assets/logo.png" alt="vue" />
    <p>Lorem ipsum dolor sit amet consectetur adipisicing</p>
  </div>
</template>

<style lang="scss" scoped>
div {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  max-width: 250px;
  background-color: #eee;
  padding-top: 10px;
  border-radius: 5px;

  img {
    padding: 5px;
    width: 200px;
    background-color: #ddd;
    border-radius: 50%;
    overflow: visible;
  }

  p {
    background-color: #aaa;
    padding: 5px;
    border-radius: 0 0 5px 5px;
    margin: 20px 0 0 0;
  }
}
</style>

<script>
export default {
  name: "FigureCom",
};
</script>
