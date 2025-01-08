<template>
  <div class="git">
    <input type="text" v-model="username" />
    <button @click="getRepos">Get Repos</button>
    <div v-for="repo in repos" :key="repo">
      <h4>{{ repo.name }}</h4>
      <p>{{ repo.description }}</p>
    </div>
  </div>
</template>

<style lang="scss"></style>

<script>
import axios from "axios";
export default {
  name: "GithubCom",
  data() {
    return {
      username: null,
      repos: null,
    };
  },
  methods: {
    getRepos: function () {
      return axios
        .get(`https://api.github.com/users/${this.username}/repos`)
        .then((response) => {
          this.repos = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>
