<template>
  <div class="password">
    <h1>Show / Hide Password</h1>
    <form>
      <input :type="fieldType" placeholder="Type your password" />
      <button @click.prevent="switchField">{{ buttonText }}</button>
    </form>
  </div>
</template>

<style lang="scss" scoped>
form {
  text-align: center;

  input {
    padding: 0 15px;
    height: 46px;
    background-color: #efefef;
    border: 1px solid #aaa;

    &:focus {
      outline: none;
    }
  }

  button {
    width: 60px;
    height: 48px;
    border-color: transparent;
    padding: 5px 10px;
    background-color: #2196f3;
    color: #fff;
    font-weight: bold;
    cursor: pointer;

    &:focus {
      outline: none;
    }
  }
}
</style>

<script>
export default {
  name: "PassCom",
  data() {
    return {
      fieldType: "password",
      buttonText: "Show",
    };
  },
  methods: {
    switchField() {
      this.fieldType = this.fieldType === "password" ? "text" : "password";
      this.switchText();
    },
    switchText() {
      this.buttonText = this.fieldType === "password" ? "Show" : "Hide";
    },
  },
};
</script>
