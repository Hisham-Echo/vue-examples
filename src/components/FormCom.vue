import FormCom from '@/components/FormCom.vue';
<template>
  <div class="form">
    <form action="" method="post" @submit="validateForm">
      <div class="error-list">
        <div class="error" v-for="error in formErrors" :key="error">
          {{ error }}
        </div>
      </div>
      <div class="form-group">
        <label for="username">Username </label>
        <input
          type="text"
          name="username"
          class="form-input"
          v-model="username"
        />
      </div>
      <div class="form-group">
        <label for="subjetc">Subject </label>
        <input
          type="text"
          name="username"
          class="form-input"
          v-model="subject"
        />
      </div>
      <div class="form-group">
        <label for="message">Message </label>
        <textarea
          name="message"
          class="form-input"
          v-model="message"
        ></textarea>
      </div>
      <div class="form-group">
        <input type="submit" class="send-button" value="Send" />
      </div>
    </form>
  </div>
</template>

<style lang="scss" scoped>
* {
  box-sizing: border-box;
}

.form {
  text-align: center;
  margin: 20px auto;
}

form {
  width: 500px;
  margin: 20px auto;

  .error-list .error {
    padding: 15px;
    background-color: rgba(244, 67, 54, 0.14);
    color: #f44336;
    margin-bottom: 15px;
  }

  .form-group {
    margin: 20px;

    label {
      display: block;
      margin-bottom: 15px;
    }

    .form-input {
      padding: 10px 15px;
      background-color: #efefef;
      border: 1px solid #ccc;
      width: 100%;
    }

    textarea {
      height: 120px;
      resize: none;
    }

    .send-button {
      display: block;
      background-color: #2196f3;
      color: #fff;
      border-color: transparent;
      padding: 10px 20px;
      width: 100%;
      font-size: 24px;
    }
  }
}
</style>

<script>
export default {
  name: "FormCom",
  data() {
    return {
      formErrors: [],
      username: null,
      subject: null,
      message: null,
      maxChars: 10,
    };
  },
  methods: {
    validateForm: function (e) {
      this.formErrors = []; // reset errors list

      if (!this.username) {
        this.formErrors.push("Username Cant Be Empty");
      }
      if (!this.subject) {
        this.formErrors.push("Subject Cant Be Empty");
      }
      if (!this.message) {
        this.formErrors.push("Message Cant Be Empty");
      }

      if (this.username && this.username.length > this.maxChars) {
        this.formErrors.push(
          `Username Cant Be more than ${this.maxChars} Characters`
        );
      }

      if (!this.formErrors.length) {
        return true;
      }

      e.preventDefault();
    },
  },
};
</script>
