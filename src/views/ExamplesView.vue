<template>
  <div class="examples">
    <div class="tabs">
      <ul class="tabs-choose">
        <li
          @click="activeTab = '1'"
          :class="[activeTab === '1' ? 'active' : '']"
        >
          Card
        </li>
        <li
          @click="activeTab = '2'"
          :class="[activeTab === '2' ? 'active' : '']"
        >
          Show / Hide
        </li>
        <li
          @click="activeTab = '3'"
          :class="[activeTab === '3' ? 'active' : '']"
        >
          Color Switch
        </li>
        <li
          @click="activeTab = '4'"
          :class="[activeTab === '4' ? 'active' : '']"
        >
          Products
        </li>
        <li
          @click="activeTab = '5'"
          :class="[activeTab === '5' ? 'active' : '']"
        >
          Github
        </li>
        <li
          @click="activeTab = '6'"
          :class="[activeTab === '6' ? 'active' : '']"
        >
          Form
        </li>
        <li
          @click="activeTab = '7'"
          :class="[activeTab === '7' ? 'active' : '']"
        >
          To Do List
        </li>
      </ul>
      <div class="tabs-content">
        <div class="content-one" v-if="activeTab === '1'"><FigureCom /></div>
        <div class="content-two" v-if="activeTab === '2'"><PassCom /></div>
        <div class="content-three" v-if="activeTab === '3'">
          <ColorSwitchCom />
        </div>
        <div class="content-four" v-if="activeTab === '4'">
          <ProductPriceCom />
        </div>
        <div class="content-five" v-if="activeTab === '5'"><GithubCom /></div>
        <div class="content-five" v-if="activeTab === '6'"><FormCom /></div>
        <div class="content-five" v-if="activeTab === '7'"><ToDoListCom /></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.tabs {
  margin: 0;
  text-align: left;
  display: flex;
}

ul.tabs-choose {
  margin-bottom: 0;
  display: flex;
  flex-flow: column;
  height: calc(100vh - 90px);
  background-color: #eee;
  overflow-y: auto;
  li {
    width: 100px;
    display: inline-block;
    padding: 10px 20px;
    background-color: #ddd;
    cursor: pointer;
    opacity: 0.3;
  }

  li.active {
    opacity: 1;
  }
}

.tabs-content {
  background-color: #ccc;
  margin: 0 auto;
  padding: 20px;
  flex-grow: 1;
  height: calc(100vh - 90px - 40px);
  overflow-y: auto;
}
</style>

<script>
import FigureCom from "@/components/FigureCom.vue";
import PassCom from "@/components/PassCom.vue";
import ColorSwitchCom from "@/components/ColorSwitchCom.vue";
import ProductPriceCom from "@/components/ProductPriceCom.vue";
import GithubCom from "@/components/GithubCom.vue";
import FormCom from "@/components/FormCom.vue";
import ToDoListCom from "@/components/ToDoListCom.vue";

export default {
  name: "ExamplesView",
  data() {
    return {
      activeTab: "7",
    };
  },
  components: {
    FigureCom,
    PassCom,
    ColorSwitchCom,
    ProductPriceCom,
    GithubCom,
    FormCom,
    ToDoListCom,
  },
  methods: {},
};
</script>
