import { default } from '../components/FigureCom.vue';
<template>
  <h1>This is an about page</h1>
  <div class="about">
    <FigureCom src="../assets/logo.png" alt="vue" v-for="i in 10" :key="i" />
  </div>
</template>

<style>
h1 {
  margin-top: 20px;
}
.about {
  display: flex;
  padding-bottom: 20px;
  gap: 20px;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>

<script>
import FigureCom from "@/components/FigureCom.vue";

export default {
  name: "AboutView",
  components: {
    FigureCom,
  },
};
</script>
