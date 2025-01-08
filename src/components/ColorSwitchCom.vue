<template>
  <div class="switch" :style="{ '--main-color': color }">
    <ul class="switch-colors">
      <li data-color="#b71540" @click="updateColor" class="active"></li>
      <li data-color="#0c2461" @click="updateColor"></li>
      <li data-color="#3c6382" @click="updateColor"></li>
      <li data-color="#079992" @click="updateColor"></li>
      <li data-color="#e58e26" @click="updateColor"></li>
    </ul>
    <div class="changes">
      <div>change</div>
      <div>change</div>
      <div>change</div>
      <div>change</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.switch {
  text-align: center;
  padding: 20px;
}

.switch-colors {
  list-style: none;
  padding: 0;
  margin: 20px;

  li {
    transition: all 0.2s ease-in-out;
    opacity: 0.5;
    width: 20px;
    height: 20px;
    border: 1px solid #eee;
    background-color: #ddd;
    display: inline-block;
    cursor: pointer;

    &.active {
      opacity: 1;
    }

    &:first-child {
      background-color: #b71540;
    }

    &:nth-child(2) {
      background-color: #0c2461;
    }

    &:nth-child(3) {
      background-color: #3c6382;
    }

    &:nth-child(4) {
      background-color: #079992;
    }

    &:last-child {
      background-color: #e58e26;
    }
  }
}

.changes {
  overflow: hidden;

  div {
    transition: all 0.2s ease-in-out;
    background-color: var(--main-color);
    color: #fff;
    padding: 20px 0;
    text-align: center;
    float: left;
    width: calc(97% / 4);

    &:not(:last-of-type) {
      margin-right: 1%;
    }
  }
}
</style>

<script>
export default {
  name: "ColorSwitchCom",
  data() {
    return {
      color: "#b71540",
    };
  },
  methods: {
    updateColor: function (event) {
      this.color = event.target.getAttribute("data-color");
      // remove active class
      let lis = event.target.parentElement.children;
      for (let i = 0; i < lis.length; i++) {
        lis[i].removeAttribute("class");
      }
      // add active class
      event.target.setAttribute("class", "active");
    },
  },
};
</script>
